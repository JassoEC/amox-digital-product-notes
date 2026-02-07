# Decisiones de UX Clave

Este documento registra **decisiones de experiencia de usuario que no son accidentales**.
No describen gustos visuales ni patrones de moda,
sino **criterio aplicado para reducir fricción cognitiva**
y preservar el control narrativo del usuario.

Cada decisión aquí documentada existe para:
- reducir decisiones innecesarias
- evitar administración de estado
- respetar límites técnicos reales
- no interferir con el canal de comunicación

---

## No eliminación

AMOX no permite eliminar productos, categorías o eventos.

La exclusión ocurre por **no selección**, no por borrado.

### Justificación

- Eliminar introduce decisiones irreversibles.
- Obliga al usuario a administrar estado.
- Aumenta ansiedad operativa (“¿lo borro o no?”).

La no selección:
- mantiene el sistema simple
- evita errores
- respeta el uso esporádico y de baja energía

---

## Fotos

AMOX **no envía imágenes** ni orquesta su envío.

El envío de imágenes ocurre únicamente mediante el
**share nativo del sistema**
y siempre como una **acción explícita del usuario**.

En el mejor de los casos,
el usuario puede enviar **una sola imagen por vez**,
según las capacidades del sistema operativo
y de la aplicación de mensajería.

AMOX no controla:
- cuántas imágenes se envían
- el orden
- ni el comportamiento del adjunto

Si se sugiere el envío de una imagen,
AMOX lo hace **de forma opcional y explícita**,
limitándose a **una sola imagen preseleccionada**
proveniente de las fotos asociadas al producto.

AMOX complementa esta acción
preparando el texto del mensaje en el **portapapeles**,
pero el envío final ocurre fuera de la aplicación.

### Justificación

- El sistema operativo impone límites reales al envío de imágenes.
- Simular envío masivo o control visual rompe expectativas.
- El usuario debe decidir conscientemente cuándo adjuntar una imagen.
- El share nativo preserva el control narrativo y el contexto del chat.

AMOX acompaña la preparación del mensaje,
pero **no gestiona ni optimiza el envío visual**.

---

## Mensajes

AMOX prepara mensajes como **texto editable**,
no como envíos automáticos ni definitivos.

El texto preparado puede:
- copiarse al portapapeles
- compartirse mediante el share nativo del sistema

Ambas acciones son explícitas y paralelas.

### Justificación

- El canal final define el formato real.
- AMOX no controla ni simula el comportamiento del chat.
- Mantener el texto editable preserva flexibilidad y control.

---

## Formato de texto (WhatsApp)

AMOX puede aplicar **optimizaciones de formato de texto**
pensadas para mejorar la legibilidad del mensaje en WhatsApp
(por ejemplo, saltos de línea o énfasis visual).

Estas optimizaciones se basan en el
**comportamiento actual de la plataforma**
a la fecha de implementación (enero de 2026).

AMOX **no garantiza la permanencia de este formato**.

La sintaxis utilizada por WhatsApp:
- no es un estándar documentado
- no está bajo control de AMOX
- puede cambiar sin previo aviso

Si la plataforma modifica su comportamiento,
el mensaje preparado por AMOX seguirá siendo válido como texto,
aunque el formato visual pueda degradarse o desaparecer.

### Justificación

- El valor principal está en la claridad del contenido, no en el estilo.
- Depender de sintaxis no oficial introduce fragilidad.
- Declarar esta limitante evita falsas expectativas.

AMOX optimiza el formato **mientras es posible**,
pero **no depende ni promete estabilidad visual futura**.

---

## Elementos contextuales del mensaje

AMOX puede sugerir ciertos elementos alrededor del mensaje principal,
pero **ninguno es obligatorio ni fijo**.

Estos elementos incluyen:
- saludo inicial
- cabeceras contextuales (categorías, eventos o temporadas)
- cierre del mensaje
- datos del negocio (firma, contacto, ubicación)

Todos comparten el mismo comportamiento:

- son **sugeridos**, no impuestos
- son **editables**
- son **descartables**
- existen solo si aportan claridad en ese contexto

No forman parte de una plantilla rígida
ni de una estructura global obligatoria.

### Justificación

- No todas las conversaciones requieren saludo o cierre.
- No todo mensaje necesita contexto adicional.
- El tono y la estructura dependen del momento, no de la aplicación.
- Forzar estos elementos rompe la naturalidad conversacional.

AMOX propone,
pero el usuario decide qué conservar,
qué ajustar
y qué omitir antes del envío.

---

## Compartir como acción final

El acto de compartir marca el **límite explícito de AMOX**.

Antes del share:
- preparación
- ajuste
- decisión consciente

Después del share:
- AMOX no interviene
- el control pasa completamente al canal

### Justificación

- Refuerza el rol auxiliar del producto.
- Evita confusión sobre automatización.
- Preserva continuidad cognitiva con la conversación.

---

## Regla derivada de UX

> Si una decisión de UX obliga al usuario a  
> administrar estado, confirmar en exceso  
> o asumir capacidades que dependen del canal  
> o del sistema operativo,  
> esa decisión es incorrecta para AMOX.
