# Curso Completo: Cómo usar Claude
### De cero a avanzado — Chat, Cowork y Código

---

## Sobre este curso

Claude es una IA desarrollada por Anthropic. A diferencia de un buscador o una app de automatización, Claude es un asistente de lenguaje: entiende instrucciones complejas, mantiene contexto a lo largo de una conversación y puede ayudarte a pensar, escribir, analizar y programar.

Este curso cubre la plataforma claude.ai desde sus funciones más básicas hasta los usos avanzados de sus tres módulos principales: **Chat**, **Cowork** y **Código**.

**Lo que vas a poder hacer al terminar:**
- Usar Chat para resolver tareas reales con instrucciones precisas
- Usar Cowork para crear espacios de trabajo con contexto persistente (Proyectos)
- Usar Código para programar, depurar y analizar datos sin necesidad de ser desarrollador

**Tiempo estimado:** 4–6 horas (puedes hacerlo por módulos)

**Prerequisito:** ninguno. Solo una cuenta en claude.ai.

---

## Cómo está organizado el curso

```
Módulo 0 — Conoce la plataforma (15 min)
    ↓
Módulo 1 — Chat: de básico a avanzado (90 min)
    ↓
Módulo 2 — Cowork / Proyectos: de básico a avanzado (60 min)
    ↓
Módulo 3 — Código: de básico a avanzado (90 min)
    ↓
Módulo 4 — Flujos combinados y casos reales (45 min)
```

---

# Módulo 0 — Conoce la plataforma

## La pantalla principal

Cuando abres claude.ai, encontrarás:

| Elemento | Dónde está | Para qué sirve |
|---|---|---|
| **Nuevo chat** | Panel izquierdo, arriba | Iniciar una conversación nueva desde cero |
| **Buscar** | Panel izquierdo | Buscar dentro de tus conversaciones anteriores |
| **Personalizar** | Panel izquierdo | Configurar tu nombre, tono preferido e instrucciones que Claude siempre recordará |
| **Chats** | Panel izquierdo | Historial de conversaciones recientes |
| **Proyectos** | Panel izquierdo | Espacios de trabajo con contexto guardado (ver Módulo 2) |
| **Artefactos** | Panel izquierdo | Documentos, código y contenido generado que puedes guardar |
| **Chat / Cowork / Código** | Pestañas superiores | Los tres modos de interacción (ver cada módulo) |
| **Campo de texto** | Centro-abajo | Donde escribes tu mensaje o adjuntas archivos |
| **Ícono de micrófono** | Campo de texto, derecha | Entrada por voz |
| **Selector de modelo** | Campo de texto | Cambiar entre versiones de Claude (Sonnet, Opus, Haiku) |

## Los tres modelos de Claude

| Modelo | Velocidad | Capacidad | Mejor para |
|---|---|---|---|
| **Claude Haiku** | Muy rápido | Alta (básica) | Tareas simples, respuestas rápidas, borrador inicial |
| **Claude Sonnet** | Rápido | Muy alta | La mayoría de tareas cotidianas — el balance ideal |
| **Claude Opus** | Más lento | Máxima | Análisis complejos, razonamiento profundo, documentos largos |

> **Regla práctica:** Empieza siempre con Sonnet. Si necesitas más profundidad, cambia a Opus. Si solo necesitas algo rápido y sencillo, usa Haiku.

## Qué puedes adjuntar

Claude puede leer y procesar:
- **Documentos:** PDF, Word (.docx), TXT, Markdown
- **Imágenes:** PNG, JPG, GIF, WebP (las analiza visualmente)
- **Código:** cualquier lenguaje (.py, .js, .ts, .sql, etc.)
- **Hojas de cálculo:** CSV (en texto plano)
- **Páginas web:** puedes pegar URLs en algunos contextos

---

# Módulo 1 — Chat

> El módulo de **Chat** es la conversación directa con Claude. Sin configuraciones especiales, sin contexto guardado: le hablas, te responde. Es el punto de entrada para el 90% de los usos.

---

## Nivel Básico — Primeras conversaciones

### 1.1 Tu primer mensaje

El error más común al empezar: escribir como si fuera Google.

| ❌ Prompt básico | ✅ Prompt efectivo |
|---|---|
| "resumen ejecutivo" | "Resume este texto en 5 bullets para un gerente que no estuvo en la reunión. Máximo 80 palabras." |
| "email para cliente" | "Escribe un email de seguimiento para un cliente que no respondió en 3 días. Tono profesional. Objetivo: reagendar una llamada. Máximo 100 palabras." |
| "explícame machine learning" | "Explícame qué es el machine learning como si tuviera experiencia en marketing pero cero en tecnología. Usa una analogía con publicidad." |

---

### 1.2 Adjuntar archivos en Chat

**Cómo hacerlo:**
1. Haz clic en el ícono `+` en el campo de texto
2. Selecciona el archivo desde tu computadora
3. El archivo aparece como chip adjunto sobre el campo de texto
4. Escribe tu instrucción y envía

**Ejemplo — Analizar un documento:**
```
[adjuntas el PDF del reporte trimestral]

Analiza este reporte y dame:
1. Los 3 hallazgos más importantes
2. Cualquier dato que parezca inconsistente o sorprendente
3. Las 2 preguntas que haría un CEO en la siguiente reunión

Formato: bullets cortos, lenguaje ejecutivo.
```

**Ejemplo — Analizar una imagen:**
```
[adjuntas captura de pantalla de un error]

¿Qué significa este error y cuál es el primer paso para resolverlo?
No soy desarrollador — explícamelo en términos simples.
```

**Ejemplo — Analizar varias imágenes a la vez:**
```
[adjuntas 3 capturas de pantalla de diferentes pasos de un flujo]

Estas imágenes muestran el proceso de checkout de mi app.
Identifica los puntos donde un usuario podría confundirse o abandonar.
Dame recomendaciones concretas de UX para cada paso.
```

---

### 1.3 Iterar en la misma conversación

Claude recuerda todo lo que dijiste en la conversación actual. Úsalo a tu favor.

**Flujo de 3 mensajes:**

```
Mensaje 1:
"Escribe el borrador de una propuesta de consultoría para una startup de 
logística. Tono profesional. Problema que resuelven: entregas de última 
milla. Longitud: 1 página."

── Claude responde con el borrador ──

Mensaje 2:
"Bien. Ahora hazlo 30% más corto y agrega una sección de 
'Por qué nosotros' de 3 bullets al final."

── Claude ajusta ──

Mensaje 3:
"Perfecto. Dame 3 opciones de asunto de email para enviar esta propuesta."
```

> **Regla de oro:** Cada mensaje de corrección debe decir **qué** cambiar, no solo que algo está mal. "Hazlo más corto" funciona. "No me gusta" no ayuda.

---

## Nivel Intermedio — Control y precisión

### 1.4 Darle un Rol a Claude

Asignarle un rol cambia radicalmente el tipo de respuesta que obtienes.

**Estructura:**
```
"Actúa como [rol específico]. [Tu pedido]."
```

**Ejemplos de roles y cuándo usarlos:**

| Rol | Cuándo usarlo | Prompt de ejemplo |
|---|---|---|
| Coach de carrera | Preparar entrevistas, decisiones laborales | "Actúa como un coach de carrera con 15 años de experiencia en RRHH. Voy a una entrevista de gerente de ventas. Hazme las 5 preguntas más difíciles y dame feedback de mis respuestas." |
| Abogado corporativo | Revisar contratos, entender cláusulas | "Actúa como abogado corporativo. Explícame esta cláusula de confidencialidad en lenguaje simple y dime si hay algo inusual: [pega la cláusula]" |
| Crítico editorial | Mejorar textos | "Actúa como editor jefe de una revista de negocios. Lee este artículo y dame 5 cambios concretos para hacerlo más convincente." |
| Analista financiero | Interpretar datos | "Actúa como CFO de una PYME. Tengo estos datos de flujo de caja del último trimestre. ¿Qué me dicen y qué debería preocuparme?" |
| Profesor socrático | Aprender sin que te den la respuesta | "Actúa como un profesor socrático. Quiero entender por qué mi estrategia de precios no está funcionando. No me des la respuesta — hazme preguntas que me lleven a verlo yo mismo." |
| Cliente difícil | Preparar negociaciones | "Actúa como un comprador corporativo muy exigente. Voy a presentarte mi propuesta de servicio. Interrumpe cuando algo no te convenza y haz las objeciones más duras." |

---

### 1.5 Controlar el formato de salida

Claude puede darte la misma información en formatos completamente distintos.

**Pide el formato explícitamente:**

```
"Dame los 5 riesgos principales de este contrato en formato tabla:
Riesgo | Impacto (alto/medio/bajo) | Recomendación"
```

```
"Resume la reunión en formato de acta ejecutiva:
Fecha / Asistentes / Decisiones tomadas / Próximos pasos con responsable y fecha"
```

```
"Escribe el plan de proyecto en formato Gantt simplificado:
Tarea | Duración | Responsable | Dependencias"
```

**Formatos disponibles:**

| Formato | Cuándo pedirlo |
|---|---|
| Tabla | Comparaciones, datos estructurados |
| Bullets numerados | Pasos secuenciales, listas de acción |
| Bullets sin número | Características, puntos independientes |
| Párrafos corridos | Textos para publicar, narrativa |
| JSON / XML | Datos estructurados para sistemas |
| Email / carta | Comunicación formal |
| Guion | Presentaciones, videos, podcasts |
| Código | Ver Módulo 3 |

---

### 1.6 Restricciones: el ingrediente que más se olvida

Las restricciones acotan la respuesta y eliminan el relleno.

**Restricciones de largo:**
```
"...en máximo 150 palabras"
"...en 3 oraciones, no más"
"...en exactamente 5 bullets"
```

**Restricciones de tono:**
```
"...tono ejecutivo, sin tecnicismos"
"...como si le hablaras a alguien de 12 años"
"...directo y sin rodeos, nada de frases de relleno"
```

**Restricciones de contenido:**
```
"...sin mencionar precios"
"...sin inventar datos — si no sabes algo, indícalo"
"...no uses la palabra 'sinergia' ni jerga corporativa"
```

**Ejemplo combinado:**
```
"Escribe un mensaje de LinkedIn para conectar con un reclutador de tecnología.
Tono: directo y humano, no corporativo.
Largo: máximo 3 oraciones.
No menciones que estoy buscando trabajo activamente.
No uses frases como 'espero que estés bien' o 'aprovecho este medio'."
```

---

## Nivel Avanzado — Técnicas de poder en Chat

### 1.7 Chain of Thought — Pedirle que piense antes de responder

Para problemas complejos, pídele a Claude que muestre su razonamiento antes de darte la conclusión. Esto mejora la calidad significativamente.

**Cómo activarlo:**
```
"Antes de responder, piensa paso a paso en voz alta.
Muéstrame tu razonamiento y luego dame tu conclusión."
```

**Ejemplo — Toma de decisión:**
```
"Tengo que elegir entre dos proveedores de software.
Proveedor A: $800/mes, buen soporte, integración nativa con nuestro CRM.
Proveedor B: $500/mes, soporte solo por email, requiere desarrollo para integrarse.

Antes de recomendarme algo, piensa en voz alta:
- ¿Qué factores debería considerar?
- ¿Qué información te falta?
- ¿Cuál sería tu razonamiento?

Luego dame tu recomendación con justificación."
```

**Ejemplo — Análisis de comunicación:**
```
"Lee este email de un cliente [pega el email].

Antes de responderme, analiza en voz alta:
- ¿Cuál es la queja real debajo de lo que dice explícitamente?
- ¿Qué emoción predomina?
- ¿Qué quiere que pase?

Luego escribe el borrador de respuesta."
```

---

### 1.8 Panel de expertos — Múltiples perspectivas en un solo prompt

Pídele a Claude que te dé varias voces distintas sobre el mismo tema.

**Ejemplo:**
```
"Voy a presentarte una idea de negocio. Quiero que me des 3 perspectivas,
una a la vez:
1. Primero como un inversor de capital de riesgo escéptico
2. Luego como un cliente potencial del producto
3. Finalmente como un competidor del sector

Mi idea: [descripción de tu idea]

Empieza con el inversor."
```

**Ejemplo — Abogado del diablo:**
```
"Actúa como el crítico más severo de esta estrategia.
Tu trabajo es encontrar todos los puntos débiles, supuestos incorrectos
y riesgos que estamos ignorando. Sé directo y no me ahorres nada.

[pega tu estrategia]"
```

---

### 1.9 Instrucciones permanentes (Personalizar)

En el panel izquierdo → **Personalizar** puedes escribir instrucciones que Claude leerá en cada conversación nueva, sin que tengas que repetirlas.

**Cómo acceder:**
`Panel izquierdo → Personalizar → "Instrucciones para Claude"`

**Ejemplo de configuración personal:**
```
Mi nombre es Mateo. Soy gerente de operaciones en una empresa de logística 
de 80 personas en México.

Cuando me respondas:
- Español latinoamericano, sin regionalismos de España
- Ve directo al punto — no repitas mi pregunta ni hagas introducción larga
- Si me das listas, máximo 5 puntos
- Si no estás seguro de un dato, dímelo explícitamente antes de continuar
- Prefiero respuestas accionables sobre teoría
- Cuando algo tenga pros y contras, dámelos en tabla
```

**Ejemplo de configuración para educadores:**
```
Soy profesora de secundaria en Colombia, área de ciencias.
Mis alumnos tienen entre 13 y 16 años.

Cuando me ayudes a crear contenido educativo:
- Lenguaje accesible para adolescentes, sin simplificar el rigor conceptual
- Incluye siempre un ejemplo de la vida cotidiana por concepto
- Si me das actividades, indica el tiempo estimado y el material necesario
- Prefiero actividades que promuevan pensamiento crítico sobre memorización
```

---

### 1.10 Control de alucinaciones

Claude puede generar información incorrecta que suena convincente. Estas técnicas lo reducen:

**Declara incertidumbre:**
```
"Cuando no estés seguro de un dato, márcalo con [verificar] al final de la oración."
```

**Lista supuestos:**
```
"Antes de responder, lista los 3 supuestos principales que estás haciendo."
```

**Separa hechos de inferencias:**
```
"En tu respuesta, diferencia claramente entre:
- Lo que es un hecho verificable
- Lo que es una inferencia o estimación tuya
- Lo que es una recomendación basada en tu criterio"
```

**Pide rutas de verificación:**
```
"Para cada dato estadístico que menciones, dime cómo podría verificarlo
(qué buscar, en qué tipo de fuente)."
```

---

# Módulo 2 — Cowork (Proyectos)

> **Cowork** es el módulo de Proyectos de Claude. A diferencia del Chat donde cada conversación empieza desde cero, en un Proyecto puedes guardar contexto, documentos e instrucciones que Claude recordará en todas las conversaciones dentro de ese espacio.

---

## Cuándo usar Proyectos vs Chat normal

| Usa Chat normal cuando... | Usa Proyectos cuando... |
|---|---|
| Es una tarea puntual y única | Trabajas en algo durante días o semanas |
| No necesitas que Claude "te conozca" | Claude necesita saber quién eres y qué estás construyendo |
| Es una pregunta independiente | Las conversaciones se relacionan entre sí |
| Estás explorando | Estás produciendo trabajo serio |

---

## Nivel Básico — Crear y configurar tu primer Proyecto

### 2.1 Crear un Proyecto

1. Panel izquierdo → **Proyectos** → **Nuevo proyecto**
2. Asígnale un nombre claro: "Lanzamiento Producto Q2", "Libro de Prompting", "Cliente Empresa X"
3. Accede al proyecto → verás el panel de configuración en la parte superior

### 2.2 Las instrucciones del Proyecto — el corazón de Cowork

Las instrucciones son el briefing permanente que Claude lee antes de cada respuesta dentro del proyecto. Aquí defines quién eres, para qué es el proyecto, cómo quieres que responda y qué no debe hacer.

**Ejemplo — Proyecto para crear un curso:**
```
Eres el asistente de contenido para el curso "¿Cómo comunicarte con la IA?" 
dirigido a profesionales latinoamericanos de 25–55 años sin base técnica.

Contexto del proyecto:
- El curso tiene 3 audiencias: trabajadores del conocimiento, educadores, 
  y líderes/gerentes
- Tono: cercano, práctico, sin jerga técnica
- Idioma: español latinoamericano neutro
- Entregables principales: módulos de contenido, ejemplos antes/después, 
  labs y material de marketing

Cuando te pida ayuda con contenido:
- Siempre pregunta para qué audiencia específica es
- Usa ejemplos cotidianos, no abstractos
- Prioriza lo accionable sobre lo teórico
- Si algo puede decirse en 50 palabras, no uses 150
```

**Ejemplo — Proyecto para gestión de clientes:**
```
Soy consultor de estrategia independiente. Este proyecto es para gestionar 
las propuestas y comunicaciones con mis clientes activos.

Clientes activos:
- Cliente A: empresa de retail, transformación digital
  Contacto: Directora de Operaciones — tono formal, orientado a procesos
- Cliente B: startup de fintech, estrategia de crecimiento
  Contacto: CEO — tono dinámico, orientado a velocidad
- Cliente C: empresa familiar, proyecto de sucesión
  Contacto: Director General — tono cálido, sensibilidad familiar

Regla crítica: nunca mezcles información entre clientes.
Si no especifico el cliente al que me refiero, pregúntame antes de responder.
```

---

### 2.3 Subir documentos al Proyecto

Dentro del proyecto puedes subir archivos que Claude leerá como parte de su contexto base en todas las conversaciones.

**Documentos útiles para subir:**
- Tu CV o bio profesional
- Brief del proyecto o del cliente
- Guías de estilo o tono de marca
- Glosario de términos del sector
- Transcripciones de reuniones anteriores
- Reportes o análisis de referencia

**Cómo subirlos:**
`Dentro del proyecto → ícono de adjuntar en el panel superior → selecciona el archivo`

**Ejemplo de uso con documento subido:**
```
[tienes subido el brief del cliente y su último reporte anual]

Con base en el brief y el reporte que tienes en contexto, 
redacta el email de propuesta inicial.
Que demuestre que leímos sus materiales y entendemos su situación específica.
No uses lenguaje genérico de consultoría.
```

---

## Nivel Intermedio — Proyectos como espacios de trabajo reales

### 2.4 Múltiples conversaciones dentro de un Proyecto

Dentro de un proyecto puedes tener varias conversaciones separadas, todas con acceso al mismo contexto base. Esto te permite organizar el trabajo por tema sin que se mezclen.

**Organización sugerida:**
```
Proyecto: Lanzamiento Producto Q2
├── Conversación: Estrategia de contenido
├── Conversación: Emails de campaña
├── Conversación: Copy para landing page
├── Conversación: Scripts para redes sociales
└── Conversación: FAQ del producto
```

Todas comparten el briefing del producto, pero cada una tiene su hilo independiente.

---

### 2.5 Proyecto como "segundo cerebro" — guardar decisiones y convenciones

Usa las instrucciones del proyecto para registrar decisiones ya tomadas que Claude no debe cuestionar ni repetir.

**Ejemplo — Proyecto de blog:**
```
BLOG DE LIDERAZGO PARA EJECUTIVOS LATAM — CONVENCIONES

VOZ Y TONO:
- Primera persona del plural cuando hablo de experiencias compartidas
- Directo y sin rodeos — el lector es gerente, tiene poco tiempo
- Nunca usamos: "potenciar", "en el marco de", "sinergia", "robusto"
- Cerramos cada artículo con una pregunta que invite a reflexionar

ESTRUCTURA DE ARTÍCULOS:
- Título: pregunta o afirmación provocadora (máximo 10 palabras)
- Intro: el problema o tensión que resuelve el artículo (2–3 oraciones)
- Cuerpo: máximo 3 ideas con un ejemplo real cada una
- Cierre: síntesis en 1 párrafo + pregunta final

TEMAS YA PUBLICADOS (no repetir ángulo):
- Liderazgo en incertidumbre (enero 2025)
- Por qué los gerentes evitan los conflictos (febrero 2025)
- El mito de la multitarea ejecutiva (marzo 2025)
```

---

### 2.6 Proyecto colaborativo (Plan Pro / Team)

Con el plan Pro o Team puedes compartir proyectos con personas de tu equipo. Todos comparten el mismo contexto base y pueden abrir conversaciones propias dentro del proyecto.

**Instrucciones recomendadas para proyectos de equipo:**
```
PROYECTO COMPARTIDO — EQUIPO DE CONTENIDO

Miembros: Ana (estrategia), Luis (redacción), Sofía (diseño)

Convenciones:
- Al inicio de cada mensaje indica tu nombre y el tipo de tarea
- Borradores: [BORRADOR] al inicio del título
- Textos aprobados: [FINAL] al inicio del título
- Si necesitas input de otro miembro, menciona su nombre

Cuando Ana pide: análisis estratégico, formato ejecutivo
Cuando Luis pide: redacción, estilo y estructura
Cuando Sofía pide: descripciones visuales, referencias de diseño
```

---

## Nivel Avanzado — Proyectos como sistemas

### 2.7 Proyecto como base de conocimiento corporativo

Sube todos los documentos del área y úsalo como repositorio inteligente que responde en lenguaje natural.

**Ejemplo — Proyecto de RRHH:**

Documentos subidos:
- Manual del empleado (PDF)
- Política de vacaciones y permisos
- Escala salarial por nivel
- Procedimiento de evaluación de desempeño
- Guía de onboarding

Instrucciones:
```
Eres el asistente del área de RRHH. Tienes acceso a todos los documentos 
de políticas y procedimientos de la empresa.

Cuando alguien te haga una pregunta:
1. Responde SOLO con base en los documentos disponibles
2. Cita el documento y sección donde encontraste la información
3. Si la respuesta no está en los documentos, dilo claramente y 
   sugiere a quién consultar
4. No interpretes ni extrapoles más allá de lo que dicen los documentos
```

Uso cotidiano:
```
¿Cuántos días de vacaciones le corresponden a un empleado 
que lleva 3 años y 4 meses en la empresa?
```

---

### 2.8 Proyecto como asistente de onboarding

Crea un proyecto para que los nuevos miembros del equipo puedan hacer preguntas en lenguaje natural sin leer 50 páginas de documentación.

**Instrucciones del proyecto:**
```
Eres el asistente de bienvenida para nuevos miembros del equipo de [empresa].

Documentos disponibles:
- Historia y cultura de la empresa
- Estructura del equipo y roles
- Proyectos activos y su estado
- Herramientas que usamos y cómo acceder
- Preguntas frecuentes de los primeros 30 días

Tu objetivo: que cualquier persona nueva pueda hacer preguntas en lenguaje 
natural y recibir respuestas claras y contextualizadas.

Si no tienes la información, di exactamente:
"Eso no está en mi contexto — consulta con [persona responsable de ese tema]."
No inventes procesos ni políticas.
```

---

# Módulo 3 — Código

> El módulo de **Código** es la pestaña especializada para trabajar con código, datos y análisis técnico. Claude puede generar código, depurarlo, explicarlo, refactorizarlo y en algunos contextos ejecutarlo. **No necesitas ser desarrollador para aprovechar este módulo.**

---

## Nivel Básico — Código sin saber programar

### 3.1 Qué puedes hacer sin saber código

Si nunca has programado, el módulo de Código te permite:
- Crear fórmulas complejas de Excel o Google Sheets
- Analizar datos de un CSV sin abrir Excel manualmente
- Automatizar tareas repetitivas con scripts simples
- Entender errores de sistemas o plataformas
- Crear visualizaciones básicas de datos

---

### 3.2 Fórmulas de Excel / Google Sheets

**Ejemplo básico:**
```
Tengo una hoja de cálculo con estas columnas:
- A: Nombre del cliente
- B: Fecha de última compra
- C: Monto de compra
- D: [quiero calcular aquí]

Crea una fórmula para la columna D que me diga si el cliente es 
"Activo" (compró en los últimos 90 días) o "Inactivo" (más de 90 días).
Explícame la fórmula antes de darla.
```

**Ejemplo avanzado:**
```
En Google Sheets tengo ventas por mes en B2:B13.
Necesito 3 fórmulas separadas:
1. Promedio mensual del año
2. Nombre del mes con mayor venta (la columna A tiene los nombres de los meses)
3. Porcentaje de crecimiento entre enero y diciembre

Explícame la lógica de cada una antes de escribirla.
```

---

### 3.3 Analizar un CSV con datos

```
[adjuntas el archivo CSV de ventas del trimestre]

Analiza estos datos y dime:
1. Total de ventas por categoría de producto
2. Los 5 clientes con mayor gasto
3. Si hay algún día de la semana con ventas significativamente más altas
4. Cualquier dato atípico o anomalía que llame la atención

No necesito código — solo el análisis en lenguaje de negocio.
```

---

### 3.4 Entender un error sin saber programar

```
Mi sistema me muestra este error y no sé qué significa:
"SQLSTATE[42S22]: Column not found: 1054 Unknown column 'user_id' in 'field list'"

Explícame en términos simples:
1. ¿Qué está pasando?
2. ¿Qué puede haberlo causado?
3. ¿Cuál es el primer paso para resolverlo?
```

---

## Nivel Intermedio — Generación y depuración de código

### 3.5 Generar código desde una descripción

No necesitas saber la sintaxis — describes el comportamiento y Claude escribe el código.

**Ejemplo — Formulario web:**
```
Necesito un formulario HTML para captura de leads.
Campos:
- Nombre completo (requerido)
- Email (requerido, con validación de formato)
- Empresa (opcional)
- Select: "¿Cómo nos conociste?" → opciones: LinkedIn / Referido / Google / Evento
- Botón: "Quiero saber más"

Estilo: limpio, fondo blanco, botón en azul oscuro (#1e3a5f).
Al enviar, muestra un mensaje de confirmación sin recargar la página.
Dame HTML, CSS y JavaScript en un solo archivo.
Explícame la estructura antes de mostrar el código.
```

**Ejemplo — Consulta SQL:**
```
Tengo dos tablas:
- clientes (id, nombre, email, ciudad, fecha_registro)
- pedidos (id, cliente_id, fecha, monto, estado)

Necesito una consulta que devuelva:
- Nombre del cliente
- Total gastado (suma de todos sus pedidos completados)
- Número de pedidos realizados
- Fecha del último pedido
- Solo clientes que hayan gastado más de $1,000 en total
- Ordenado de mayor a menor gasto

Explícame la lógica antes de escribir el SQL.
```

---

### 3.6 Depurar código — Debug

Pega el código que no funciona y el error que te da:

```
Este código de Python me da un error y no entiendo por qué.
Error: "KeyError: 'nombre'"

[pega el código]

¿Qué está fallando? Explícamelo sin asumir que soy desarrollador experto,
y dame el código corregido con los cambios marcados.
```

```
Esta fórmula de Google Sheets me devuelve #REF! y no sé por qué:
=VLOOKUP(A2, 'Hoja2'!B:D, 3, FALSE)

¿Qué está mal, por qué ocurre, y cómo la corrijo?
```

---

### 3.7 Explicar código que heredaste

```
Me pasaron este script para que lo administre y necesito entender 
exactamente qué hace antes de tocarlo.

Explícamelo de dos maneras:
1. Primero línea por línea técnicamente
2. Luego en lenguaje de negocio: qué problema resuelve y qué pasaría 
   si algo fallara

[pega el código]
```

---

### 3.8 Análisis de datos con Python

El módulo de Código puede ejecutar Python directamente. No necesitas instalar nada.

```
[adjuntas CSV con datos de ventas mensuales]

Usando Python, necesito que:
1. Calcules el margen de ganancia por mes: (ventas - costos) / ventas
2. Graficar la evolución de ventas vs costos como línea de tiempo
3. Identifiques el mes más rentable y el menos rentable
4. Proyectes cómo se vería el siguiente trimestre si la tendencia continúa

Muéstrame el código Y los resultados del análisis.
Explícame los hallazgos en lenguaje de negocio al final.
```

---

## Nivel Avanzado — Desarrollo y arquitectura

### 3.9 Construir una feature completa

```
Necesito una función en TypeScript que:
- Reciba un array de objetos: { nombre: string, email: string, fecha: Date }
- Filtre los registros de los últimos 30 días
- Los ordene por fecha descendente
- Devuelva solo los 10 más recientes
- Maneje el caso de array vacío o undefined sin romperse

Requisitos:
- Tipos TypeScript estrictos
- Tests unitarios con Jest para los casos edge
- Documentación con JSDoc

Dame primero el diseño de la función y los casos edge que cubrirás.
Luego el código completo. Luego los tests.
```

---

### 3.10 Refactorizar código existente

```
Este código funciona pero es difícil de mantener.
Quiero que lo refactorices para:
1. Eliminar la repetición (principio DRY)
2. Funciones más pequeñas con una sola responsabilidad
3. Nombres de variables autodescriptivos
4. Manejo de errores donde falta

Dame primero un diagnóstico: ¿qué problemas ves?
Luego el código refactorizado.
Luego una lista de los cambios que hiciste y por qué.

[pega el código]
```

---

### 3.11 Revisión de seguridad

```
Revisa este código desde una perspectiva de seguridad.
Busca específicamente:
- Inyección SQL
- XSS (Cross-Site Scripting)
- Datos sensibles hardcodeados
- Falta de validación de inputs del usuario
- Dependencias con vulnerabilidades conocidas

Para cada problema:
- Describe el riesgo en lenguaje simple
- Muestra el impacto potencial con un ejemplo de ataque
- Dame el código corregido con los cambios destacados

[pega el código]
```

---

### 3.12 Decisiones de arquitectura

```
Voy a construir una API REST para gestión de inventarios.
Requisitos:
- 500 usuarios concurrentes en fase inicial
- CRUD para productos, categorías y movimientos de stock
- Autenticación por JWT
- Notificaciones en tiempo real cuando el stock baja del mínimo
- Deployment en AWS

Antes de que empiece a escribir código, necesito tomar decisiones:
1. ¿Qué stack tecnológico recomiendas y por qué?
2. ¿Cómo debería estructurar los endpoints principales?
3. ¿Qué considerar para escalar después sin reescribir todo?
4. ¿Qué herramientas de monitoreo incluir desde el inicio?

Sé específico y justifica cada recomendación. Si hay trade-offs, muéstralos.
```

---

# Módulo 4 — Flujos Combinados y Casos Reales

> Aquí aprendes a usar Chat + Cowork + Código juntos para resolver problemas reales de principio a fin.

---

## Caso 1 — Lanzamiento de producto (sin equipo técnico)

**Situación:** Gerente de marketing que necesita crear una landing page, emails y análisis de resultados.

**Paso 1 — Crea un Proyecto: "Lanzamiento Producto X"**
Sube: brief del producto, guía de marca, copy de campañas anteriores.

**Paso 2 — Chat → estrategia**
```
Con base en el brief del producto que tienes en contexto,
dame la estructura de la landing page:
qué secciones debe tener, en qué orden, y cuál es el objetivo de cada una.
```

**Paso 3 — Chat → redacción**
```
Ahora redacta el copy completo de la landing page siguiendo 
la estructura que definimos. Tono de marca según el brief.
```

**Paso 4 — Código → formulario**
```
Crea el formulario HTML para la sección de registro.
Campos: nombre, email, empresa, cargo.
Botón: "Quiero acceso anticipado".
Estilo minimalista, fondo blanco, acento en azul marino.
```

**Paso 5 — Código → análisis de resultados**
```
[adjuntas CSV con datos de registros de la landing — primeros 15 días]

Analiza:
- Tasa de conversión por fuente de tráfico
- Perfil más común de quien se registra (cargo y empresa)
- Recomendación: ¿a cuál segmento enfocar los esfuerzos siguientes?
```

---

## Caso 2 — Informe ejecutivo para el board

**Situación:** Director que necesita transformar datos crudos en un reporte ejecutivo.

**Paso 1 — Código → limpiar datos**
```
[adjuntas el Excel con datos en múltiples hojas]

Consolida todos los datos de ventas en una tabla limpia.
Identifica y marca los registros con datos faltantes o inconsistentes.
```

**Paso 2 — Código → análisis y visualizaciones**
```
Con los datos limpios, genera en Python:
1. Gráfica de barras: ventas por región Q1 vs Q2
2. Tabla resumen: top 5 productos por margen
3. KPIs: crecimiento total, mejor mes, región con mayor caída
```

**Paso 3 — Chat → narrativa ejecutiva**
```
Tengo estos resultados [pega los números].

Escribe la narrativa del reporte para el board:
3 párrafos — qué pasó, por qué importa, qué hacemos ahora.
Tono: directo, orientado a decisiones. Sin eufemismos ni relleno.
```

---

## Caso 3 — Investigación de mercado completa

**Situación:** Emprendedor evaluando entrar a un nuevo sector.

**Paso 1 — Chat → framework**
```
Voy a investigar el mercado de [sector] en [país].
Dame el framework de análisis: qué dimensiones cubrir,
qué preguntas responder, y en qué orden abordarlas.
```

**Paso 2 — Chat → síntesis de reportes**
```
[adjuntas los PDFs de reportes de mercado que encontraste]

Sintetiza estos reportes en un análisis de máximo 2 páginas.
Estructura: mercado total / tendencias clave / jugadores principales /
oportunidades no atendidas / riesgos.
Cuando un dato venga de un reporte específico, cítalo.
```

**Paso 3 — Código → modelado de escenarios**
```
Con base en estos datos [pega los números clave], crea una proyección:

Escenario conservador: 2% de captura de mercado
Escenario base: 5%
Escenario optimista: 10%

Para cada uno: ingresos proyectados año 1, 2 y 3
asumiendo precio de venta de $X y costo promedio de $Y.
Muéstrame la tabla y el código Python que la generó.
```

---

# Referencia Rápida

## Frases clave por módulo

### Chat
| Necesidad | Frase |
|---|---|
| Activar razonamiento | "Piensa paso a paso antes de responder" |
| Controlar largo | "Máximo [X] palabras / oraciones / bullets" |
| Pedir alternativas | "Dame 3 versiones con enfoques distintos" |
| Iterar | "Mantén todo igual pero cambia [X]" |
| Verificar | "¿Qué supusiste para escribir esto?" |
| Resetear | "Ignora lo anterior. Empecemos de nuevo con: [...]" |
| Asignar rol | "Actúa como [experto]. [Tu pedido]." |

### Cowork / Proyectos
| Necesidad | Acción |
|---|---|
| Crear contexto base | Instrucciones del proyecto (briefing completo) |
| Agregar conocimiento | Subir documentos al proyecto |
| Separar temas | Una conversación por tema |
| Actualizar contexto | Editar las instrucciones del proyecto cuando cambien los datos |
| Colaborar en equipo | Compartir el proyecto (Plan Pro / Team) |

### Código
| Necesidad | Frase |
|---|---|
| Generar código | "Escribe [lenguaje] que haga [función]. Explica cada parte." |
| Depurar | "Este código da el error [X]. ¿Qué falla y cómo se corrige?" |
| Explicar | "Explícame este código como si no supiera programar" |
| Refactorizar | "Mejora este código. Primero dime qué problemas ves." |
| Analizar datos | "Analiza este CSV y dime [pregunta de negocio]" |
| Seguridad | "Revisa este código buscando vulnerabilidades de seguridad" |

---

## Checklist antes de enviar

```
Chat:
□ ¿Definí el entregable exacto?
□ ¿Incluí contexto: para quién, para qué?
□ ¿Especifiqué el formato de salida?
□ ¿Puse restricciones de tono y largo?

Proyectos:
□ ¿Mis instrucciones explican quién soy y para qué es el proyecto?
□ ¿Subí los documentos de referencia relevantes?
□ ¿Cada conversación tiene un tema claro?

Código:
□ ¿Describí el comportamiento esperado, no solo la tecnología?
□ ¿Mencioné el contexto técnico (lenguaje, framework)?
□ ¿Pedí que me explique antes de generar?
□ ¿Pedí manejo de errores y casos edge?
```

---

## Límites que debes conocer

| Límite | Qué significa en la práctica |
|---|---|
| **Ventana de contexto** | Claude puede leer hasta ~200,000 tokens (~150,000 palabras). Documentos muy largos pueden requerir dividirse. |
| **Sin memoria entre chats** | Cada conversación nueva empieza desde cero (usa Proyectos para persistir contexto) |
| **Datos hasta agosto 2025** | No tiene información de eventos muy recientes. Pídele que señale cuando algo puede estar desactualizado. |
| **No navega internet en tiempo real** | A menos que tenga activada la búsqueda web (disponible en algunos planes) |
| **Puede alucinar** | Siempre verifica datos críticos: cifras, nombres propios, fechas, leyes |
| **No guarda entre sesiones** | Lo que aprendiste en Chat hoy no lo recuerda mañana en un chat nuevo |