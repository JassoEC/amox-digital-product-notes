# Entidades de Dominio (MVP)

Este documento define **qué información existe realmente en AMOX**
y cómo se modela a nivel de dominio.

No describe estructuras de UI ni decisiones de persistencia.
Describe **conceptos estables del producto**
y su rol dentro de una herramienta cuyo propósito es
**preparar mensajes**, no administrar operaciones.

El objetivo del dominio en AMOX no es representar un negocio completo,
sino **sostener la preparación del mensaje**
con el menor estado posible.

---

## Criterio general de modelado

AMOX distingue explícitamente entre dos tipos de información:

1. **Información identitaria**
2. **Información operativa y contextual**

Esta distinción es intencional
y atraviesa decisiones de UX, arquitectura y persistencia.

---

## Información identitaria

La información identitaria define **quién es el negocio**
y cómo se presenta ante el cliente.

Sus características son:

- cambia poco
- se reutiliza constantemente
- no depende de una conversación específica
- no forma parte del flujo operativo del mensaje

Estas entidades:
- no se seleccionan
- no se combinan
- no forman colecciones

Existen como **una única instancia válida activa**.

---

### Entidades identitarias

#### BusinessProfile

Representa la identidad básica del negocio.

- id
- name
- description
- contactInfo (teléfono, redes, ubicación)

Su función es **dar contexto y credibilidad**,
no administrar operaciones.

---

#### BusinessPreferences

Representa decisiones generales de presentación,
no reglas de negocio.

- currency { code, symbol, position }
- tone
- usePhotoAsVisualReference

Estas preferencias:
- no automatizan comportamientos
- no imponen estructura
- solo influyen en sugerencias iniciales

---

#### MessageFooter

Representa el cierre sugerido del mensaje.

- text

No es obligatorio,
no es fijo
y puede omitirse completamente según el contexto.

---

### Comportamiento común

Las entidades identitarias:

- existen como **una sola fuente de verdad**
- no admiten múltiples versiones simultáneas
- no participan en lógica condicional compleja
- no dependen del contexto de uso inmediato

Su rol es **acompañar**, no decidir.

---

## Información operativa y contextual

La información operativa representa **qué se comunica**
en un momento específico.

Está diseñada para:

- seleccionarse
- combinarse
- variar por conversación
- usarse de forma efímera

No representa inventarios,
no representa pedidos
y no pretende reflejar estado real del negocio.

---

### Entidades operativas

#### Product

Representa un elemento comunicable,
no una unidad de inventario.

- id
- name
- description (larga)
- shortDescription (para listados)
- price
- mainPhotoId

Los productos en AMOX **existen de forma independiente**.

No requieren pertenecer a una categoría
ni a un evento o temporada para ser utilizados.

Un producto existe para **preparar mensajes claros**,
no para controlar stock, precios dinámicos o ventas.

---

#### ProductPhoto

Representa una imagen asociada a un producto.

- id
- productId
- uri
- isPrimary

Las fotos:
- no se envían automáticamente
- no forman flujos
- sirven solo como referencia visual opcional

---

#### Category

Agrupa productos por **forma de presentación comunicativa**,
no por clasificación estructural.

- id
- name
- contextualHeader

Las categorías:
- son opcionales
- no definen jerarquías
- no imponen pertenencia
- no representan taxonomía

Un producto puede:
- no pertenecer a ninguna categoría
- aparecer o no en una selección según el contexto

Su único propósito es **ayudar a preparar el mensaje**,
no ordenar el dominio.

---

#### EventSeason

Representa un **contexto de uso o situación específica**
en la que ciertos productos pueden comunicarse de forma distinta.

- id
- name
- contextualHeader

Los eventos o temporadas:
- son opcionales
- no clasifican productos
- no activan comportamientos automáticos
- no representan estado del negocio

Un producto puede:
- no estar asociado a ningún evento
- usarse dentro o fuera de un contexto temporal

Su función es **ajustar el mensaje al momento**,
no definir estructura ni reglas.

---

## Qué el dominio **no** modela

Por decisión explícita, el dominio de AMOX **no incluye**:

- clientes
- conversaciones
- mensajes enviados
- pedidos
- inventarios
- métricas
- estados de flujo
- automatizaciones

Estos conceptos:
- no reducen fricción cognitiva
- introducen complejidad innecesaria
- empujan a AMOX fuera de su rol auxiliar

---

## Regla derivada de dominio

> Si una entidad existe para administrar, automatizar  
> o representar estado externo del negocio,  
> no pertenece al dominio de AMOX.

---

## Nota de coherencia con UX y arquitectura

Este modelado permite que:

- la UX sea flexible y descartable
- el dominio permanezca estable
- la persistencia sea simple
- un backend futuro sea ligero y no decisor

El dominio no conoce:
- el canal de envío
- el sistema operativo
- el formato final del mensaje

Solo conoce **información preparada para ser comunicada**.
