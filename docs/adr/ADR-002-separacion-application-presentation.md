# ADR-002 — Separación explícita entre Application y Presentation

## Estado

Aceptada — decisión estructural

---

## Contexto

AMOX adopta una arquitectura en capas con:

- Domain
- Application
- Presentation

El dominio contiene entidades con **invariantes claras**
y representa conceptos estables del producto.
La UI, en cambio, vive en un entorno reactivo
donde los estados intermedios, parciales o inválidos
son inevitables.

Durante la implementación surgieron preguntas clave:

- ¿Debe la UI trabajar directamente con entidades de dominio?
- ¿Dónde viven los hooks y el estado reactivo?
- ¿Cómo se representan las intenciones del usuario?
- ¿Es necesario introducir ports/adapters adicionales?

Este ADR fija respuestas explícitas
para evitar ambigüedad futura.

---

## Decisión

### 1. Las entidades de dominio **no** se usan como estado editable de UI

Las entidades de dominio:

- son clases con invariantes
- asumen consistencia interna
- no toleran estados inválidos intermedios

La UI, por naturaleza:
- atraviesa estados parciales
- permite edición incompleta
- necesita flexibilidad temporal

Por lo tanto,
las entidades de dominio **no se usan**
como estado local de componentes o hooks.

---

### 2. La UI interactúa mediante *Input Models* definidos en Application

Las intenciones de cambio provenientes de la UI
se modelan como **Input Models (DTOs)** en la capa Application.

Ejemplos:
- `UpdateBusinessProfile`
- `UpdateBusinessPreferences`
- `UpdateMessageFooter`

Estos modelos:

- representan intención, no estructura de UI
- pueden aceptar invalidez parcial
- son consumidos por casos de uso
- definen la frontera de entrada al dominio

La Presentation **no conoce**
cómo se construyen las entidades de dominio.

---

### 3. El mapeo DTO → Dominio ocurre exclusivamente en Application

Los casos de uso son responsables de:

- fusionar estado actual + intención de cambio
- validar invariantes
- construir entidades de dominio válidas
- persistir resultados

Esto protege al dominio
de inconsistencias introducidas por la UI.

---

### 4. Los hooks pertenecen a Presentation, no a Application

Aunque algunos hooks:

- ejecutan casos de uso
- exponen capacidades del sistema
- no contienen JSX

siguen siendo **dependientes del framework React**,
ya que:

- viven en su ciclo de vida
- manejan estado reactivo
- existen para facilitar el consumo desde componentes

Por lo tanto:

- no existen hooks en Application
- los hooks viven en `presentation/hooks`
- Application expone solo casos de uso y modelos

---

### 5. No se introducen ports adicionales entre Presentation y Application

Se decidió **no introducir abstracciones adicionales**
entre Presentation y Application porque:

- existe un solo frontend
- no hay múltiples implementaciones en runtime
- los repositorios ya abstraen infraestructura
- no hay presión real que justifique esa complejidad

La Presentation depende directamente de Application,
respetando la *Dependency Rule*
sin sobre-ingeniería.

---

## Consecuencias

### Positivas

- Dominio protegido contra invalidez accidental
- Separación clara de responsabilidades
- Application expresa intención, no mecanismos
- Presentation actúa como adaptador explícito a React
- Menor complejidad accidental
- Código más legible y defendible

---

### Negativas / Trade-offs

- Introducción de Input Models implica más código
- Requiere disciplina en el mapeo
- Menor “comodidad inmediata” en la UI

Estos trade-offs son **aceptados**
por claridad y sostenibilidad a largo plazo.

---

## Relación con otras decisiones

- Complementa:
  - ADR-001 (identidad como *singleton lógico*)
  - ADR-PROD-001 (AMOX no automatiza)
- Alineado con:
  - `03-decisiones-ux.md`
  - `04-entidades-dominio.md`

---

## Regla derivada

> Entidades con invariantes  
> no se usan como estado editable de UI.  
>  
> La UI expresa intención.  
> Application decide.  
> Domain valida.

---

## Cierre

Esta separación no existe
para cumplir un patrón arquitectónico.

Existe para **proteger el criterio del producto**
de la naturaleza caótica de la UI
y permitir que AMOX evolucione
sin traicionar su rol auxiliar.

La arquitectura sirve al producto,
no al revés.
