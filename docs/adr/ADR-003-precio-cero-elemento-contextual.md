# ADR-003 — Precio Cero como Elemento Contextual en Mensajes

## Estado

Aceptada — decisión de renderizado, validada con observación de usuarios reales

---

## Contexto

AMOX permite preparar mensajes comerciales seleccionando **productos**, **categorías** y **eventos**.

El sistema genera un mensaje estructurado respetando el contexto narrativo de la conversación.

Durante el uso del sistema apareció un caso recurrente:

No todos los elementos que forman parte de un mensaje comercial tienen un precio explícito.

Ejemplo real:

Menú del día

• Milanesa $85
• Enchiladas $85
• Pechuga $90

Incluye:

• arroz
• frijoles
• tortillas

En este escenario:

- Los **platillos fuertes** tienen precio.
- Los **acompañamientos** forman parte del contexto de la oferta.

Sin embargo, en el modelo actual todos los elementos están representados por la entidad `Product`, que incluye el atributo `price`.

---

## Decisión

Se introduce la siguiente regla de renderizado:

```
if product.price == 0:
    hide_price()
```

Un producto con **precio cero** representa un **elemento contextual del mensaje**, no un elemento vendible.

---

## Justificación

### 1. Alternativas descartadas

Se consideraron:

1. Crear una nueva entidad (por ejemplo `Complement`)
2. Introducir productos compuestos o combos
3. Crear un bloque fijo de "Incluye" al final del mensaje

Todas introducen mayor complejidad en el dominio, más configuración para el usuario y más fricción cognitiva — lo cual contradice los principios de AMOX.

---

### 2. Resultado en el mensaje

Antes:

- Milanesa $85
- Enchiladas $85
- Arroz $0
- Frijoles $0

Después:

- Milanesa $85
- Enchiladas $85
- Arroz
- Frijoles

La narrativa del mensaje se mantiene natural.

---

### 3. Patrón habilitado

Un mismo `Product` puede representar:

1. Producto vendible
2. Complemento contextual
3. Elemento informativo

Esto permite modelar menús, combos, acompañamientos y elementos incluidos sin introducir nuevas entidades ni relaciones complejas.

---

## Consecuencias

### Positivas

**Producto**
- composición narrativa flexible del mensaje
- sin nuevas entidades ni configuración adicional

**UX**
- cero configuración adicional
- comportamiento intuitivo
- mayor flexibilidad al armar mensajes
- menor fricción cognitiva

**Ingeniería**
- el modelo de dominio no se modifica
- la persistencia no cambia
- el cambio ocurre únicamente en la lógica de renderizado del mensaje

---

### Negativas / Trade-offs

Un producto realmente gratuito también ocultará el precio.

Ejemplo: `Agua gratis` → aparece solo como `Agua`.

Este caso puede resolverse mediante texto descriptivo: `Agua (gratis)`.

El trade-off se considera aceptable frente a la simplicidad obtenida.

---

## Relación con otras decisiones

- Alineado con:
  - `02-principios-de-producto.md` (simplicidad sobre configuración)
  - `03-decisiones-ux.md` (menor fricción cognitiva)
  - `04-entidades-dominio.md` (entidad `Product` y atributo `price`)
- Coherente con:
  - ADR-001 (modelo simple, sin estados adicionales)
  - ADR-PROD-001 (AMOX no introduce complejidad que no aporta valor)

---

## En el código

La regla de renderizado vive en `presentation/hooks/message/narrative/buildProductBlock.ts`:

```ts
if (options.showPrices && product.price > 0) {
    const priceFormatted = product.price.toLocaleString('es-MX', {
        style: 'currency',
        currency: currencyCode || 'MXN',
    })
    lines.push(priceFormatted)
}
```

El dominio (`Product.ts`) almacena `price: number` sin restricción sobre cero.
La omisión del precio ocurre únicamente en la capa de presentación, sin afectar el modelo.

---

## Consecuencia observada en dominio

Durante el desarrollo existió una inconsistencia detectada a partir de observación real de usuarios:

`Product.isReadyToShow()` incluía la condición `price > 0`:

```ts
isReadyToShow(): boolean {
    return this.price > 0 && this.description != undefined && this.shortDescription != undefined
}
```

Esto mezclaba dos razones de cambio en un mismo método:

1. **Completitud del producto para catálogo** — tiene nombre, descripción, descripción corta.
2. **Precio definido** — condición que ADR-003 establece como independiente del renderizado.

Un producto contextual (precio = 0) era incorrectamente marcado como "no listo para mostrarse",
contradiciendo la decisión documentada aquí.

La corrección separó ambas responsabilidades:
- `isReadyToShow()` evalúa completitud de información, sin considerar el precio.
- La omisión del precio en el mensaje sigue siendo exclusivamente una regla de renderizado.

> Esta inconsistencia fue detectada por observación directa de uso real,
> no por revisión de código.
> Confirma que la decisión documentada en este ADR tenía implicaciones de dominio
> que no habían sido completamente resueltas en la implementación inicial.

---

## Regla derivada

> Cuando el modelo técnico ya es suficiente para representar un caso real,
> ajustar la lógica de presentación
> antes que introducir nuevas entidades o configuraciones.

---

## Cierre

El uso de **precio cero como señal contextual** permite que AMOX mantenga un modelo simple mientras aumenta la capacidad narrativa del sistema.

La decisión:

- preserva simplicidad
- evita sobreingeniería
- aumenta flexibilidad narrativa
- reduce fricción cognitiva

Esto mantiene a AMOX alineado con su rol principal:

**preparar mensajes claros para conversaciones de venta.**
