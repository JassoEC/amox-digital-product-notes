# ADR-PROD-001 — AMOX no automatiza ni sustituye al humano

## Estado

Aceptada — principio fundacional de producto

---

## Contexto

Durante la construcción inicial y la validación temprana de AMOX
se identificó un patrón claro en negocios pequeños
que venden conversando por chat:

- la venta ocurre en diálogo humano
- el principal desgaste no es la velocidad, sino la repetición
- el cansancio aparece antes del envío, no después
- las soluciones existentes fallan al imponer flujos rígidos

Las herramientas orientadas a:
- bots
- respuestas automáticas
- flujos condicionales
- integración profunda con APIs de mensajería

tienden a:
- desplazar el control narrativo fuera del usuario
- romper el contexto conversacional
- introducir complejidad técnica y mental
- convertir la herramienta en sistema decisor

Esto entra en conflicto directo con el problema validado:
**fricción cognitiva previa a responder**.

---

## Decisión

AMOX se define explícitamente como una herramienta de
**preparación de mensajes**, no de ejecución automática.

Por decisión de producto:

- ❌ AMOX no envía mensajes.
- ❌ AMOX no responde por el usuario.
- ❌ AMOX no automatiza conversaciones.
- ❌ AMOX no depende de APIs de mensajería.
- ❌ AMOX no actúa sin intervención humana explícita.

El envío ocurre siempre:
- fuera de AMOX
- en el canal elegido por el usuario
- bajo su criterio final

AMOX termina su rol **antes del envío**.

---

## Justificación

### 1. Preservar el control narrativo

La venta por chat depende del contexto,
el tono
y la lectura humana del momento.

Automatizar respuestas
reduce esa capacidad
y convierte la conversación en un flujo rígido.

---

### 2. Reducir fricción cognitiva real

El objetivo de AMOX no es decidir más rápido,
sino **pensar menos** antes de responder.

La automatización:
- introduce reglas
- exige configuración
- desplaza la carga cognitiva

AMOX reduce carga,
no la redistribuye.

---

### 3. Alinear producto con uso real observado

La validación temprana mostró que:

- los usuarios entienden y valoran que AMOX no automatice
- el producto se usa como apoyo previo al envío
- no surge la automatización como necesidad central

Forzar automatización sería
diseñar desde la ambición técnica,
no desde el uso real.

---

### 4. Proteger la claridad del producto

Automatizar implicaría:

- redefinir el dominio
- introducir estado conversacional
- agregar métricas y flujos
- convertir a AMOX en sistema central

Esto rompe la identidad del producto
y diluye su propuesta de valor.

---

## Consecuencias

### Positivas

- Identidad clara y defendible
- UX simple y predecible
- Dominio reducido y estable
- Menor complejidad técnica
- Uso inmediato sin aprendizaje pesado
- Alineación con reposo mental del usuario

---

### Negativas / Trade-offs

- No cubre casos de automatización
- No escala a operaciones masivas
- Excluye ciertos perfiles de usuario

Estos trade-offs son **intencionales y aceptados**,
porque no aportan valor al problema validado.

---

## Relación con otras decisiones

- Refuerza:
  - `00-vision.md`
  - `02-principios-de-producto.md`
  - `03-decisiones-ux.md`
- Se apoya en:
  - `01-problem-insights.md`
  - `validacion-temprana-observaciones-iniciales.md`
- Coherente con:
  - ADR-001 (identidad como *singleton lógico*)
  - ADR-002 (separación Application / Presentation)

---

## Regla derivada

> Ninguna evolución futura puede introducir  
> automatización o ejecución sin intervención humana  
> sin replantear la identidad completa de AMOX.

---

## Cierre

Esta decisión no es una limitación técnica.

Es una **posición de producto consciente**:
AMOX existe para **acompañar al humano**,
no para reemplazarlo.

Automatizar no es el siguiente paso.
Ser claro sobre dónde termina el producto, sí.
