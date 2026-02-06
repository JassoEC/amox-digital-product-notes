# AMOX — Línea de Tiempo y Maduración de Decisiones

Este documento registra **cuándo** y **por qué** se tomaron decisiones clave en AMOX, con el objetivo de demostrar que no fueron reacciones impulsivas, sino el resultado de construcción, uso real y reflexión deliberada.

---

## Diciembre 2025 – Febrero 2026  
### AMOX como app Android (estado actual)

Durante este periodo se desarrolló el núcleo funcional de AMOX como aplicación Android utilizando Expo / React Native.

**Enfoque principal**
- Construcción del core del producto.
- Claridad de límites.
- Uso inmediato sin cuentas ni backend.

**Decisiones fundacionales**
- Arquitectura en capas: Domain / Application / Presentation.
- Entidades de identidad modeladas como *singleton lógico*.
- Persistencia local diferenciada:
  - AsyncStorage para identidad.
  - SQLite para estado operativo.
- Exclusión explícita de:
  - automatización
  - bots
  - CRM
  - flujos complejos
- AMOX definido como herramienta auxiliar, no sistema central.

Este periodo corresponde a la **construcción consciente del producto base**, priorizando criterio sobre velocidad.

---

## Febrero 2026  
### Feedback en mundo real

Durante febrero de 2026 se realizaron demos y uso informal con perfiles reales de negocio.

**Observaciones confirmadas**
- El problema es real y recurrente.
- El valor está en reducir fricción cognitiva.
- AMOX es entendido como herramienta de preparación, no como automatización.
- El producto se usa sin explicación extensa.

**Decisión importante**
- No se introdujeron cambios estructurales.
- No se añadieron features por presión externa.
- El objetivo fue observar comprensión y uso, no optimizar adopción.

Este periodo se utilizó exclusivamente para **validación de rol**, no para iteración reactiva.

---

## Marzo 2026 en adelante (planeado)  
### Backend ligero y continuidad

La introducción de un backend ligero (por ejemplo, Supabase) se plantea **después** de las etapas anteriores.

**Motivación**
- Eliminar la plataforma móvil como limitante.
- Permitir continuidad (respaldo y multi‑dispositivo).
- Proteger el valor ya construido por el usuario.

**Alcance explícito**
- Respaldo remoto.
- Sincronización opcional.
- Identidad mínima por cuenta.

**Exclusiones**
- Automatización.
- Lógica de negocio en backend.
- Intervención en conversaciones.

El backend se concibe como **soporte**, no como cerebro del sistema.

---

## Nota sobre maduración de decisiones

Las decisiones clave de AMOX siguen un orden explícito:

1. Construir.
2. Usar.
3. Observar.
4. Reflexionar.
5. Evolucionar.

El espaciamiento temporal entre etapas es intencional y forma parte del **capital intelectual** del proyecto.

---

## Cierre

AMOX no se desarrolló como un experimento apresurado ni como una persecución de tendencias.

Es un ejercicio deliberado de:
- diseño de producto
- arquitectura pragmática
- toma de decisiones bajo contexto real

La línea de tiempo aquí documentada existe para preservar esa historia.