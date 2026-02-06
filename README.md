<p align="center">
  <img src="images/amox-digital.png" width="1024" height="500" alt="Amox Digital logo" />
</p>


# AMOX Digital — Product Notes

Este repositorio documenta el **diseño, las decisiones y los límites** detrás de **AMOX Digital**, una aplicación móvil orientada a apoyar la comunicación comercial de negocios pequeños que venden por chat.

No contiene el código de la aplicación.  
Contiene el **razonamiento** que la sostiene.

---

## ¿Qué es AMOX Digital?

**AMOX Digital** es una herramienta que **prepara mensajes comerciales claros y reutilizables** para conversaciones por chat (principalmente WhatsApp), sin automatizar, sin intervenir en la conversación y sin reemplazar el criterio humano.

El producto existe para reducir:
- repetición innecesaria
- desgaste mental
- errores al copiar y pegar información

AMOX **no envía mensajes**, **no automatiza respuestas** y **no administra conversaciones**.  
Su rol termina antes del envío.

> *AMOX prepara mensajes. El usuario decide cómo, cuándo y dónde enviarlos.*

---

## ¿Qué problema aborda?

En negocios pequeños y operaciones individuales, la venta ocurre conversando.

Todos los días se repite la misma información:
- precios
- disponibilidad
- horarios
- condiciones
- fotos

Esto genera fricción cognitiva, inconsistencias y pérdida de tiempo, especialmente cuando la energía mental ya es limitada.

El problema no es el canal (WhatsApp).  
El problema es **reconstruir el mismo mensaje una y otra vez**.

---

## Enfoque del producto

AMOX fue diseñado con restricciones claras:

- Uso inmediato  
- Sin cuentas  
- Sin dependencia de APIs de mensajería  
- Sin automatización  
- Sin flujos impuestos  

El producto prioriza **claridad operativa y reposo mental** sobre features extensos.

No busca escalar conversaciones.  
Busca **sostener al usuario cuando ya está cansado o cuando tiene más tareas en las que enfocarse**.

---

## ¿Qué documenta este repositorio?

Este repositorio existe para dejar rastro de:

- la visión original del producto
- el problema observado en usuarios reales
- los principios no negociables
- el alcance y los límites del MVP
- decisiones de UX
- modelado de dominio
- decisiones técnicas documentadas como ADRs
- aprendizajes obtenidos durante validación temprana

Cada documento responde a una pregunta concreta del tipo:
> *¿Por qué se decidió esto y qué se aceptó a cambio?*

---

## ¿Qué NO es este repositorio?

- No es documentación de uso
- No es material de marketing
- No es un tutorial
- No es el código fuente de la app

Es un **registro de criterio de producto e ingeniería**, pensado para ser leído con contexto, no para ser ejecutado.

---

## Vocabulario

Este repositorio utiliza algunos términos de forma **intencional y consistente**.
No funcionan como definiciones académicas, sino como **marcos de criterio**.

- **Criterio**  
  Capacidad de tomar decisiones conscientes bajo restricciones reales.
  En AMOX, el criterio importa más que la cantidad de features.

- **Trade-offs**  
  Consecuencias aceptadas explícitamente al tomar una decisión.
  Toda decisión documentada en este repositorio implica algo que se gana y algo que se pierde.

- **Reposo mental**  
  Alivio cognitivo inmediato al reducir repetición, memoria y reconstrucción innecesaria.
  Es una propuesta de valor central del producto.

- **Control narrativo**  
  El usuario mantiene siempre el control sobre qué se dice, cómo se dice y cuándo se envía.
  AMOX no sustituye ni automatiza ese rol.

- **Preparar mensajes**  
  Construir mensajes claros y reutilizables **antes del envío**.
  El envío ocurre siempre fuera de AMOX, en el canal elegido por el usuario.

- **No automatiza**  
  Principio fundacional del producto.
  AMOX no responde, no decide y no actúa sin intervención humana.

- **Fuera de alcance**  
  Funcionalidades deliberadamente excluidas para proteger claridad, foco y bajo costo cognitivo.
  No es falta de capacidad técnica, es decisión de producto.

- **Validación temprana**  
  Señales cualitativas obtenidas con usuarios reales para confirmar o descartar hipótesis, no métricas de escala ni crecimiento.

- **Decisiones en el tiempo**  
  Registro de cómo el criterio del producto madura conforme cambia el contexto,
  sin asumir progreso lineal ni acumulación automática de features.

---

## Estructura

- `/docs`  
  - `adr/` → decisiones técnicas documentadas  
  - `validacion/` → aprendizajes con usuarios reales  
  - visión, problema, principios, alcance, UX y dominio del producto

La estructura está pensada para leerse de forma secuencial, no como referencia aislada.

---

## Línea de tiempo y maduración de decisiones

AMOX no se diseñó en una sola iteración.

Existe un documento que registra **cómo fueron cambiando y afinándose las decisiones**
conforme aparecieron validaciones reales, límites técnicos y claridad de rol del producto.

Este registro no enumera features,
documenta **criterio aplicado bajo contexto real**.

→ [`09-linea-de-tiempo-y-maduracion.md`](/docs/09-linea-de-tiempo-y-maduracion.md)

---

## Estado del proyecto

AMOX Digital se encuentra en **fase de validación temprana con usuarios reales**.

El contenido de este repositorio se actualiza conforme:
- aparecen nuevas señales de uso
- se toman decisiones adicionales
- se confirman o descartan hipótesis

---

## Intención del repositorio

Este repositorio forma parte de un portafolio profesional.

Su objetivo no es demostrar cantidad de código, sino **capacidad para diseñar, acotar y sostener un producto real**, tomando decisiones conscientes frente a trade-offs técnicos y de negocio.

---

## Lectura recomendada

Si quieres entender AMOX desde el criterio (no desde features):

1. Visión del producto  
   → [`00-vision.md`](/docs/00-vision.md)

2. Problema observado e insights reales  
   → [`01-problem-insights.md`](/docs/01-problem-insights.md)

3. Principios no negociables  
   → [`02-principios-de-producto.md`](/docs/02-principios-de-producto.md)

4. Qué entra y qué queda fuera del MVP  
   → [`05-mvp-scope.md`](/docs/05-mvp-scope.md)  
   → [`06-no-scope.md`](/docs/06-no-scope.md)

5. Decisiones técnicas clave (ADRs)  
   → [`ADR-PROD-001`](/docs/adr/ADR-PROD-001-amox-no-automatiza.md)  
   → [`ADR-001`](/docs/adr/ADR-001-identidad-singleton-logico.md)  
   → [`ADR-002`](/docs/adr/ADR-002-separacion-application-presentation.md)

---

> Nota: Este repositorio está escrito en español por coherencia con el contexto actual del producto.
> Una versión en inglés se preparará cuando el caso de estudio esté estabilizado.

---

## Autor

Emanuel Campos

---

> El software no se define sólo por lo que hace, sino por lo que **decide no hacer**.
