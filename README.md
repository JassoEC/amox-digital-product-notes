<p align="center">
  <img src="images/amox-digital.png" width="440" alt="Amox Digital logo" />
</p>


# AMOX Digital — Product Notes

Este repositorio documenta el **diseño, las decisiones y los límites** detrás de **Amox Digital**, una aplicación móvil orientada a apoyar la comunicación comercial de negocios pequeños que venden por chat.

No contiene el código de la aplicación.  
Contiene el **razonamiento** que la sostiene.

---

## ¿Qué es Amox Digital?

**Amox Digital** es una herramienta que **prepara mensajes comerciales claros y reutilizables** para conversaciones por chat (principalmente WhatsApp), sin automatizar, sin intervenir en la conversación y sin reemplazar el criterio humano.

El producto existe para reducir:
- repetición innecesaria
- desgaste mental
- errores al copiar y pegar información

Amox **no envía mensajes**, **no automatiza respuestas** y **no administra conversaciones**.  
Su rol termina antes del envío.

> *Amox prepara mensajes. El usuario decide cómo, cuándo y dónde enviarlos.*

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

Amox fue diseñado con restricciones claras:

- Uso inmediato  
- Sin cuentas  
- Sin dependencia de APIs de mensajería  
- Sin automatización  
- Sin flujos impuestos  

El producto prioriza **claridad operativa y reposo mental** sobre features extensos.

No busca escalar conversaciones.  
Busca **sostener al usuario cuando ya está cansado**.

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

## Estructura

/docs
/adr → decisiones técnicas documentadas
/validacion → aprendizajes con usuarios reales
vision, problema, principios, alcance, UX, dominio


La estructura está pensada para leerse de forma secuencial, no como referencia aislada.

---

## Estado del proyecto

Amox Digital se encuentra en **fase de validación temprana con usuarios reales**.

El contenido de este repositorio se actualiza conforme:
- aparecen nuevas señales de uso
- se toman decisiones adicionales
- se confirman o descartan hipótesis

---

## Intención del repositorio

Este repositorio forma parte de un portafolio profesional.

Su objetivo no es demostrar cantidad de código, sino **capacidad para diseñar, acotar y sostener un producto real**, tomando decisiones conscientes frente a trade-offs técnicos y de negocio.

---

## Autor

Emanuel Campos

---

> El software no se define solo por lo que hace,  
> sino por lo que **decide no hacer**.
