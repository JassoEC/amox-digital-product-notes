# Alcance del MVP

Este documento define **qué incluye explícitamente el MVP de AMOX**
y, por consecuencia directa, **qué no incluye**.

El alcance no está definido por capacidad técnica,
sino por **criterio de producto**:
solo entra aquello que reduce fricción cognitiva inmediata
en el momento previo al envío de un mensaje.

---

## Objetivo del MVP

Permitir que negocios pequeños
**respondan mejor y más rápido por chat**
sin automatizar,
sin imponer flujos
y sin administrar conversaciones.

El MVP existe para validar:
- comprensión del rol del producto
- utilidad en uso real
- reducción de carga mental operativa

No para maximizar adopción,
ni para escalar operaciones.

---

## Incluido en el MVP

### Preparación de mensajes por selección

El usuario puede preparar un mensaje seleccionando:
- productos
- categorías (opcionales)
- eventos o temporadas (opcionales)

La selección es libre y contextual.
No existe dependencia estructural entre estos elementos.

---

### Productos y contenido comunicable

- Creación y edición de productos
- Descripciones largas y cortas
- Precio como información comunicable (no calculable)
- Asociación opcional de fotos como referencia visual

Los productos existen para **comunicar**, no para administrar inventario.

---

### Agrupadores contextuales

- Categorías como agrupadores de forma
- Eventos o temporadas como agrupadores de situación de uso

Ambos son:
- opcionales
- no jerárquicos
- no taxonómicos
- no obligatorios para usar productos

---

### Elementos sugeridos del mensaje

AMOX puede sugerir:
- saludo inicial
- cabeceras contextuales
- cierre del mensaje
- datos del negocio

Todos estos elementos son:
- sugeridos
- editables
- descartables

Nunca forman una plantilla obligatoria.

---

### Preparación de texto

- Mensaje preparado como **texto editable**
- Copia al portapapeles
- Uso del texto fuera de AMOX

AMOX no envía mensajes
ni controla el canal final.

---

### Share nativo del sistema

- Uso del share nativo como acción final
- Envío controlado por el sistema operativo y la app destino
- Sin dependencia de APIs de mensajería

AMOX no simula ni reemplaza el comportamiento del canal.

---

### Uso opcional de imágenes

- Sugerencia explícita y opcional de **una sola imagen**
- Imagen preseleccionada desde las fotos del producto
- Envío siempre mediante share nativo

AMOX no gestiona envío masivo
ni controla adjuntos.

---

### Optimización de formato (WhatsApp)

- Optimización oportunista del formato de texto
- Basada en comportamiento actual de la plataforma
- Sin garantía de estabilidad futura

El mensaje sigue siendo válido como texto
aunque el formato visual cambie.

---

### Configuración mínima

- Preferencias globales básicas
- Sin flujos de administración
- Sin configuración obligatoria previa al uso

El producto debe ser usable
desde el primer momento.

---

## Qué queda explícitamente fuera del MVP

Este MVP **no incluye**:

- envío automático de mensajes
- automatización de conversaciones
- uso de WhatsApp API u otras APIs de mensajería
- gestión de clientes
- historial de conversaciones
- pedidos
- inventarios
- métricas o dashboards
- campañas
- flujos complejos
- plantillas rígidas
- eliminación de entidades
- backend obligatorio
- cuentas multiusuario

Estas exclusiones son **intencionales**
y coherentes con el rol de AMOX
como herramienta auxiliar.

---

## Regla de inclusión al MVP

> Si una capacidad no reduce fricción cognitiva inmediata  
> o empuja a AMOX hacia administración, automatización  
> o control del canal,  
> no pertenece al MVP.
