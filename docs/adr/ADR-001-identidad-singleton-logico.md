# ADR-001 — Entidades de Identidad como *Singleton Lógico*

## Estado

Aceptada — decisión fundacional

---

## Contexto

AMOX maneja dos tipos de información claramente diferenciados:

1. **Identidad del negocio**
2. **Estado operativo y contextual del mensaje**

La identidad del negocio incluye información que:
- define quién es el negocio ante el cliente
- cambia poco en el tiempo
- se reutiliza constantemente
- no depende de una conversación específica

Ejemplos claros de este tipo de información son:
- perfil del negocio
- preferencias generales de presentación
- cierre o firma del mensaje

Modelar esta información como colecciones editables,
listas o entidades múltiples
introduce estados inválidos,
decisiones innecesarias
y complejidad que no aporta valor al problema central.

---

## Decisión

Las entidades que representan **identidad del negocio** en AMOX
se modelan como **singleton lógico**.

Esto implica que:

- existe **una única instancia válida activa**
- no se crean múltiples versiones simultáneas
- no forman colecciones
- no participan en flujos de selección

Las entidades afectadas por esta decisión son:

- `BusinessProfile`
- `BusinessPreferences`
- `MessageFooter`

Estas entidades se modifican de forma explícita,
pero no se eligen ni se combinan en tiempo de uso.

---

## Justificación

### 1. Naturaleza de la información

La identidad:
- no es operativa
- no es contextual
- no rota por conversación

Representa decisiones fundacionales,
no estado transitorio.

---

### 2. Reducción de estados inválidos

Permitir múltiples instancias de identidad:
- obliga a decidir cuál es la “activa”
- introduce conflictos innecesarios
- aumenta carga cognitiva

El singleton lógico elimina esta clase de problemas
desde el modelo.

---

### 3. Coherencia con UX

En la experiencia de usuario:

- el perfil no se selecciona
- la firma no se elige entre varias
- las preferencias no se combinan

El modelo de dominio refleja exactamente ese comportamiento.

---

### 4. Claridad arquitectónica

Modelar identidad como singleton lógico permite:

- contratos simples (`load` / `save`)
- persistencia atómica
- ausencia de queries complejas
- dominio estable y fácil de razonar

---

## Consecuencias

### Positivas

- Dominio más simple y explícito
- Menos estados posibles
- UX alineada con el modelo
- Persistencia clara y predecible
- Facilita evolución futura (respaldo, sync)

---

### Negativas / Trade-offs

- No se soportan múltiples perfiles por negocio
- No se permite versionado histórico de identidad
- Menor flexibilidad para escenarios multi-marca

Estos trade-offs son **intencionales y aceptados**,
ya que no aportan valor al problema validado.

---

## Relación con otras decisiones

- Alineado con:
  - `02-principios-de-producto.md`
  - `03-decisiones-ux.md`
  - `04-entidades-dominio.md`
- Complementado por:
  - ADR-002 (separación Application / Presentation)
  - ADR-PROD-001 (AMOX no automatiza)

---

## Regla derivada

> Si una entidad define identidad y cambia raramente,  
> debe modelarse como *singleton lógico*,  
> no como colección editable.

---

## Cierre

Esta decisión no es una optimización técnica.

Es una **afirmación de rol del producto**:
AMOX acompaña la comunicación,
no administra estructuras complejas.

Modelar identidad como *singleton lógico*
protege esa claridad desde el dominio.
