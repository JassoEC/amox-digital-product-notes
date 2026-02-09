# AMOX — Línea de Tiempo y Maduración de Decisiones

Este documento registra **cuándo y por qué** se tomaron decisiones clave en AMOX,
con el objetivo de demostrar que no fueron reacciones impulsivas,
sino el resultado de **construcción, uso real y reflexión deliberada**.

No describe una evolución lineal de funcionalidades.
Describe la **maduración del criterio del producto**
conforme se aclaró su rol, sus límites y su contexto real de uso.

---

## Diciembre 2025 – Febrero 2026  
### AMOX como app Android (estado actual)

Durante este periodo se desarrolló el núcleo funcional de AMOX
como aplicación Android utilizando Expo / React Native.

### Enfoque principal

- Construcción del core del producto.
- Claridad deliberada de límites.
- Uso inmediato sin cuentas ni backend.

El objetivo de esta etapa no fue escalar adopción,
sino **definir correctamente el rol del producto**.

### Decisiones fundacionales

- Arquitectura en capas: Domain / Application / Presentation.
- Entidades de identidad modeladas como *singleton lógico*.
- Persistencia local diferenciada:
  - AsyncStorage para identidad.
  - SQLite para estado operativo.
- Uso del share nativo como frontera explícita del sistema.
- Exclusión consciente de:
  - automatización
  - bots
  - CRM
  - flujos complejos
- AMOX definido como **herramienta auxiliar**, no como sistema central.

Este periodo corresponde a la **construcción consciente del producto base**,
priorizando criterio y coherencia sobre velocidad de entrega.

---

## Febrero 2026  
### Uso real y validación de rol

Durante febrero de 2026 se realizaron demos
y uso informal con perfiles reales de negocio,
principalmente operaciones individuales
que venden conversando por chat.

### Observaciones confirmadas

- El problema es real y recurrente.
- El valor principal está en reducir fricción cognitiva.
- AMOX es entendido como herramienta de preparación,
  no como automatización ni sistema de mensajería.
- El producto se utiliza sin explicación extensa.
- El valor aparece en momentos de cansancio real.

### Decisión importante

- No se introdujeron cambios estructurales.
- No se añadieron features por presión externa.
- No se amplió el alcance del producto.

Este periodo se utilizó exclusivamente para **validar el rol correcto de AMOX**,
no para iterar de forma reactiva.

---

## Febrero – Marzo 2026  
### Explicitación de criterio y límites

A partir de la validación de rol,
el foco se desplazó **del código a la claridad conceptual**.

Durante esta etapa se documentaron explícitamente:

- visión del producto
- problema observado e insights reales
- principios no negociables
- decisiones clave de UX
- entidades de dominio y su alcance
- delimitación del MVP y exclusiones explícitas
- roadmap condicionado por criterio

El producto no cambió de forma sustancial.
Cambió su **nivel de explicitud y defendibilidad**.

Esta etapa transformó AMOX de:
> “una app funcional”

en:
> **un producto con criterio claro y límites explícitos**.

---

## Marzo 2026 en adelante (planeado)  
### Backend ligero y continuidad

La introducción de un backend ligero
(por ejemplo, Supabase)
se plantea **solo después** de haber fijado el rol del producto.

### Motivación

- Eliminar la plataforma móvil como limitante.
- Permitir continuidad (respaldo y multi-dispositivo).
- Proteger el valor ya construido por el usuario.

### Alcance explícito

- Respaldo remoto.
- Sincronización opcional.
- Identidad mínima por cuenta.

### Exclusiones explícitas

- Automatización.
- Lógica de negocio en backend.
- Intervención en conversaciones.
- Dashboards, métricas o workflows.

El backend se concibe como **soporte de continuidad**,
no como cerebro del sistema.

---

## Nota sobre maduración de decisiones

Las decisiones clave de AMOX siguen un orden explícito y no intercambiable:

1. Construir.
2. Usar.
3. Observar.
4. Reflexionar.
5. Documentar.
6. Evolucionar solo si el criterio ya está maduro.

El espaciamiento temporal entre etapas es **intencional**
y forma parte del **capital intelectual del proyecto**.

---

## Cierre

AMOX no se desarrolló como un experimento apresurado
ni como una persecución de tendencias.

Es un ejercicio deliberado de:
- diseño de producto
- arquitectura pragmática
- y toma de decisiones bajo contexto real

Esta línea de tiempo existe
para **preservar esa historia**
y proteger al producto de desviarse en el futuro.
