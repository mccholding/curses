# Curso Completo: Cómo usar Claude
### De cero a avanzado — Chat, Proyectos, Claude Code, Agentes y Conectores

---

## Sobre este curso

Claude es una IA desarrollada por Anthropic. A diferencia de un buscador o una app de automatización, Claude es un asistente de lenguaje: entiende instrucciones complejas, mantiene contexto a lo largo de una conversación y puede ayudarte a pensar, escribir, analizar, programar y operar herramientas externas.

Este curso cubre el ecosistema Claude completo: la plataforma **claude.ai** (Chat, Proyectos, Artifacts), la herramienta para desarrollo **Claude Code**, la creación e implementación de **agentes** por rol —desde C-Level hasta analista—, y la integración con servicios externos vía **Skills, MCP y Conectores**.

**Lo que vas a poder hacer al terminar:**
- Usar Chat para resolver tareas reales con instrucciones precisas
- Usar Proyectos para crear espacios de trabajo con contexto persistente
- Usar Claude Code para programar, depurar y operar tu codebase desde la terminal o tu IDE
- Diseñar agentes adecuados al rol y nivel de autonomía (C-Level → Analista)
- Conectar Claude con tus herramientas (Gmail, Drive, Figma, Vercel, etc.) vía Skills y MCP
- Combinar todo en flujos reales de trabajo

**Tiempo estimado:** 8–10 horas (puedes hacerlo por módulos)

**Prerequisitos:**
- Para Módulos 0–2: ninguno, solo una cuenta en claude.ai
- Para Módulos 3–4: cuenta en claude.ai y disposición a instalar Claude Code (terminal/IDE)
- Para Módulo 5: cuentas en los servicios externos que quieras conectar

---

## Cómo está organizado el curso

```
Módulo 0 — Conoce la plataforma (15 min)
    ↓
Módulo 1 — Chat: de básico a avanzado (90 min)
    ↓
Módulo 2 — Proyectos: contexto persistente y colaboración (60 min)
    ↓
Módulo 3 — Claude Code (CLI/IDE): asistencia para desarrollo (120 min)
    ↓
Módulo 4 — Agentes: del C-Level al Analista (90 min)
    ↓
Módulo 5 — Skills, MCP y Conectores (60 min)
    ↓
Módulo 6 — Flujos combinados y casos reales (45 min)
```

---

# Módulo 0 — Conoce la plataforma

## El ecosistema Claude

Antes de entrar en cada módulo, conviene entender que **Claude no es un solo producto** sino un conjunto coordinado:

| Producto | Dónde vive | Para quién | Pago |
|---|---|---|---|
| **claude.ai** (Chat, Proyectos, Artifacts) | Navegador, app de escritorio, móvil | Cualquier profesional | Free / Pro / Team / Enterprise |
| **Claude Code** | Terminal, VS Code, JetBrains | Desarrolladores y equipos técnicos | Incluido en Pro y planes superiores |
| **API Anthropic** | Tus propias aplicaciones | Empresas que integran Claude en su producto | Pay-per-use |
| **Conectores / MCP** | Dentro de claude.ai y Claude Code | Cualquier usuario que quiera leer/escribir en servicios externos | Según el plan |

Este curso se enfoca en los tres primeros, en ese orden.

---

## La pantalla principal de claude.ai

Cuando abres claude.ai, encontrarás:

| Elemento | Dónde está | Para qué sirve |
|---|---|---|
| **Nuevo chat** | Panel izquierdo, arriba | Iniciar una conversación nueva desde cero |
| **Buscar** | Panel izquierdo | Buscar dentro de tus conversaciones anteriores |
| **Personalizar** | Panel izquierdo | Configurar tu nombre, tono preferido e instrucciones permanentes |
| **Chats** | Panel izquierdo | Historial de conversaciones recientes |
| **Proyectos** | Panel izquierdo | Espacios de trabajo con contexto guardado (ver Módulo 2) |
| **Artifacts** | Panel izquierdo | Documentos, código y contenido generado que puedes guardar y reutilizar |
| **Campo de texto** | Centro-abajo | Donde escribes tu mensaje, adjuntas archivos o activas herramientas |
| **Selector de modelo** | Campo de texto | Cambiar entre versiones de Claude (Sonnet / Opus / Haiku) |
| **Selector de herramientas** | Campo de texto | Activar búsqueda web, modo investigación, ejecución de código, etc. |

## Los tres modelos de Claude

Anthropic publica tres familias de modelos. Los nombres genéricos se mantienen estables; las versiones cambian (revisa siempre en claude.ai cuál está vigente).

| Modelo | Velocidad | Capacidad | Mejor para |
|---|---|---|---|
| **Claude Haiku** | Muy rápido | Alta (básica) | Tareas simples, respuestas rápidas, borrador inicial, automatizaciones de alto volumen |
| **Claude Sonnet** | Rápido | Muy alta | La mayoría de tareas cotidianas — el balance ideal |
| **Claude Opus** | Más lento | Máxima | Análisis complejos, razonamiento profundo, documentos largos, programación de arquitectura |

> **Regla práctica:** Empieza siempre con Sonnet. Si necesitas más profundidad, cambia a Opus. Si solo necesitas algo rápido y sencillo, usa Haiku.

**Modo de pensamiento extendido (Extended Thinking):** Algunos modelos permiten activar un razonamiento más profundo (Claude "piensa" antes de responder). Útil para problemas matemáticos, decisiones complejas y código difícil. Aparece como toggle en el selector de modelo cuando está disponible.

**Fast mode (Opus):** Modo opcional con Opus que mantiene la capacidad de razonamiento pero con respuestas más rápidas. Útil cuando necesitas la inteligencia de Opus sin esperar.

---

## Qué puedes adjuntar

Claude puede leer y procesar directamente:
- **Documentos:** PDF, Word (.docx), TXT, Markdown
- **Imágenes:** PNG, JPG, GIF, WebP (las analiza visualmente)
- **Código:** cualquier lenguaje (.py, .js, .ts, .sql, .go, .rs, etc.)
- **Hojas de cálculo:** CSV, XLSX
- **Páginas web:** URLs con búsqueda web activada
- **Audio:** transcripciones automáticas (en planes que lo soportan)

## Herramientas integradas (en claude.ai)

Activables desde el campo de texto:

| Herramienta | Para qué |
|---|---|
| **Búsqueda web** | Consultar internet en tiempo real |
| **Investigación (Research)** | Búsqueda profunda multi-paso con citas |
| **Code execution** | Ejecutar Python sobre tus archivos (CSV, Excel, etc.) |
| **Conectores** | Leer/escribir en Gmail, Calendar, Drive, Figma, etc. (ver Módulo 5) |

---

## Límites técnicos que debes conocer

| Límite | Qué significa |
|---|---|
| **Ventana de contexto** | Los modelos actuales soportan entre 200,000 y 1,000,000 de tokens según versión. En la práctica: documentos muy largos caben en una sola conversación, pero conviene dividir cuando excedes ~70% del límite. |
| **Sin memoria entre chats por defecto** | Cada conversación nueva empieza desde cero — usa Proyectos (Módulo 2) o memoria de Claude Code (Módulo 3) para persistir contexto. |
| **Knowledge cutoff** | Varía por modelo — revisa en claude.ai. Para eventos recientes, activa búsqueda web. |
| **Puede alucinar** | Siempre verifica datos críticos: cifras, nombres propios, fechas, leyes, citas. Aprende a pedir verificación (Módulo 1, sección 1.10). |

---

# Módulo 1 — Chat

> El módulo de **Chat** es la conversación directa con Claude en claude.ai. Sin configuraciones especiales, sin contexto guardado entre conversaciones: le hablas, te responde. Es el punto de entrada para el 90% de los usos.

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

### 1.4 Tareas técnicas sin saber programar

Aunque Claude Code es la herramienta seria de desarrollo (Módulo 3), en el Chat puedes resolver tareas técnicas cotidianas sin abrir nada más.

**Fórmulas de Excel / Google Sheets:**
```
Tengo una hoja con columnas:
- A: Nombre del cliente
- B: Fecha de última compra
- C: Monto

Crea la fórmula para una columna D que diga "Activo" si compró en los
últimos 90 días, "Inactivo" si no. Explícame la fórmula antes de darla.
```

**Análisis de CSV con ejecución de código (activa "Code execution"):**
```
[adjuntas CSV de ventas del trimestre]

Analiza estos datos y dime:
1. Total de ventas por categoría de producto
2. Los 5 clientes con mayor gasto
3. Si hay algún día de la semana con ventas significativamente más altas
4. Cualquier dato atípico

Muéstrame también un gráfico de barras de ventas por categoría.
No necesito código — solo el análisis en lenguaje de negocio.
```

**Entender un error sin ser desarrollador:**
```
Mi sistema me muestra este error:
"SQLSTATE[42S22]: Column not found: 1054 Unknown column 'user_id'"

Explícame en términos simples:
1. ¿Qué está pasando?
2. ¿Qué puede haberlo causado?
3. ¿Cuál es el primer paso para resolverlo?
```

---

## Nivel Intermedio — Control y precisión

### 1.5 Darle un Rol a Claude

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
| Cliente difícil | Preparar negociaciones | "Actúa como un comprador corporativo muy exigente. Voy a presentarte mi propuesta. Interrumpe cuando algo no te convenza y haz las objeciones más duras." |

---

### 1.6 Controlar el formato de salida

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
| Artifact | Documento o app interactiva (Claude lo crea en panel lateral) |

---

### 1.7 Restricciones: el ingrediente que más se olvida

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

### 1.8 Artifacts — documentos y apps en el panel lateral

Cuando Claude genera algo sustancial (un documento, un componente React, un análisis), aparece en un panel a la derecha como **Artifact**: lo puedes editar, descargar, compartir y reutilizar en otras conversaciones.

**Cuándo pedir explícitamente un artifact:**
```
"Crea este documento como artifact para que pueda editarlo después."
```

**Tipos de artifact que Claude puede crear:**
- Documentos Markdown
- Código (HTML/CSS/JS, Python, React, etc.) — algunos son ejecutables en el navegador
- Diagramas (Mermaid)
- SVG / gráficos
- Apps interactivas simples

**Ejemplo — Mini-app interactiva:**
```
Construye una calculadora de tasa de conversión: ingresa visitas y conversiones,
muestra el porcentaje y un benchmark de la industria SaaS.
Hazla un artifact en React con estilo limpio.
```

---

## Nivel Avanzado — Técnicas de poder en Chat

### 1.9 Chain of Thought — Pedirle que piense antes de responder

Para problemas complejos, pídele a Claude que muestre su razonamiento antes de darte la conclusión. Esto mejora la calidad significativamente.

**Cómo activarlo en el prompt:**
```
"Antes de responder, piensa paso a paso en voz alta.
Muéstrame tu razonamiento y luego dame tu conclusión."
```

> **Tip:** Si tu plan/modelo lo soporta, activa **Extended Thinking** en el selector de modelo. Es lo mismo pero hecho por el sistema, sin "ensuciar" tu respuesta visible.

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

---

### 1.10 Panel de expertos — Múltiples perspectivas en un solo prompt

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

### 1.11 Instrucciones permanentes (Personalizar)

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

---

### 1.12 Control de alucinaciones

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

**Combina con búsqueda web:**
```
Activa búsqueda web (botón en el campo de texto) y pídele:
"Busca fuentes recientes para cada cifra que menciones. Cítalas con URL."
```

---

# Módulo 2 — Proyectos

> Los **Proyectos** son espacios de trabajo con contexto persistente. A diferencia del Chat donde cada conversación empieza desde cero, en un Proyecto puedes guardar instrucciones, documentos y conversaciones que Claude recordará en todas las interacciones dentro de ese espacio.

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

### 2.2 Las instrucciones del Proyecto — el corazón del módulo

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
- Entregables: módulos de contenido, ejemplos antes/después,
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
- Liderazgo en incertidumbre
- Por qué los gerentes evitan los conflictos
- El mito de la multitarea ejecutiva
```

---

### 2.6 Proyecto colaborativo (Plan Pro / Team)

Con Pro o Team puedes compartir proyectos con personas de tu equipo. Todos comparten el mismo contexto base y pueden abrir conversaciones propias dentro del proyecto.

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

# Módulo 3 — Claude Code (CLI / IDE)

> **Claude Code** es la herramienta de Anthropic para trabajar con código a nivel profesional. Vive en tu terminal o dentro de tu editor (VS Code, JetBrains). A diferencia de claude.ai, Claude Code **lee y escribe directamente en tu sistema de archivos**, ejecuta comandos, corre tests, y trabaja sobre tu repo completo.
>
> No reemplaza claude.ai — lo complementa. Úsalo cuando tu trabajo viva en código, no en documentos.

---

## Nivel Básico — Qué es y cómo empezar

### 3.1 Quién debería usar Claude Code

| Si eres... | ¿Te sirve Claude Code? |
|---|---|
| Desarrollador (cualquier seniority) | Sí, es la herramienta principal |
| Data analyst / data scientist | Sí, para análisis sobre tus propios scripts y notebooks |
| Product manager técnico | Sí, para revisar PRs, leer codebase, escribir specs sobre el código |
| DevOps / SRE | Sí, especialmente con MCP de infraestructura |
| Diseñador / Marketing | No, quédate con claude.ai y conectores |
| Operaciones / Finanzas | Probablemente no — usa Chat + Proyectos |

> **Regla:** Si tu trabajo abre regularmente una terminal o un IDE, Claude Code te va a cambiar el día a día. Si no, no lo necesitas.

---

### 3.2 Instalación

**Requisitos:** Node.js o un runtime compatible. Cuenta en claude.ai (incluido en Pro y superior).

**Pasos:**
1. Instala el paquete de Claude Code siguiendo la guía oficial en docs.anthropic.com
2. En tu terminal, ejecuta `claude` (o el comando equivalente que indique la guía)
3. En el primer arranque te pedirá autenticarte con tu cuenta
4. (Opcional) Instala la extensión para VS Code o JetBrains desde el marketplace del IDE

**Verificación rápida:**
```
claude
> hola, ¿qué directorio ves?
```

Claude debería responder describiendo el contenido del directorio donde lo lanzaste.

---

### 3.3 La diferencia fundamental con claude.ai

| claude.ai | Claude Code |
|---|---|
| Lee archivos que **tú adjuntas** | Lee todos los archivos del proyecto cuando los necesita |
| Sus cambios viven en el chat | Modifica directamente archivos en tu disco |
| No ejecuta comandos de tu máquina | Puede ejecutar bash, tests, builds, git |
| Cada conversación arranca desde cero | Persiste contexto vía `CLAUDE.md` y memoria |
| No tiene "agentes" especializados | Tiene subagents, hooks, skills, MCP nativo |
| Pensado para tareas puntuales | Pensado para flujos largos de desarrollo |

---

### 3.4 Tu primera sesión: pedir un cambio simple

Estando en la raíz de un proyecto:

```
claude
> Lee la estructura del proyecto y dime qué tipo de app es,
  qué framework usa, y cómo se ejecuta.
```

Luego, un cambio:

```
> En el archivo de configuración, cambia el puerto por defecto de 3000 a 4000
  y verifica que no haya referencias hardcodeadas a 3000 en otros archivos.
```

Claude:
1. Lee la estructura
2. Identifica el archivo de config
3. Hace el cambio
4. Busca referencias a 3000 en todo el repo
5. Te pregunta antes de modificar nada sensible

---

## Nivel Intermedio — Customize: el menú clave

El menú `Customize` (también accesible vía slash-commands) es donde Claude Code se transforma de "asistente genérico" a "asistente que conoce tu proyecto y tu forma de trabajar".

> **Guía detallada del menú Customize:** Consulta el archivo complementario `claude-code-customize-guia.md` para el desglose por opción. Esta sección cubre el resumen estratégico.

### 3.5 Resumen del menú Customize

| Opción | Para qué | Determinismo |
|---|---|---|
| **Output styles** | Cambiar el "modo" de respuesta (Default / Explanatory / Learning) | Sugerencia |
| **Agents (subagents)** | Especialistas con contexto aislado y system prompt propio | Sugerencia |
| **Hooks** | Reglas que SIEMPRE deben ejecutarse en eventos del ciclo de vida | Determinista |
| **Memory** (`CLAUDE.md`) | Contexto persistente del proyecto que Claude lee al iniciar | Sugerencia |
| **Permissions** | Qué herramientas puede usar Claude sin pedir confirmación | Determinista |
| **MCP servers** | Conexiones a servicios externos (Figma, Vercel, etc.) | N/A |
| **Manage plugins** | Instalar/desinstalar plugins (que pueden traer subagents, skills, MCPs bundleados) | N/A |
| **Output styles personalizados** | Crear tus propios "modos" para respuestas | Sugerencia |

---

### 3.6 `CLAUDE.md`: el archivo más importante

`CLAUDE.md` es el archivo de contexto persistente del proyecto. Claude Code lo lee automáticamente al iniciar cada sesión.

**Niveles:**
- **Project memory** — `./CLAUDE.md` en la raíz del repo. Se commitea con git, se comparte con el equipo.
- **User memory** — `~/.claude/CLAUDE.md`. Personal, válido para todos tus proyectos.
- **Local project** — `./CLAUDE.local.md`. Privado del proyecto pero no commiteado.

**Plantilla mínima recomendada:**

```markdown
# [Nombre del proyecto]

## Stack
- [Framework principal y versión]
- [Base de datos]
- [Servicios externos relevantes]

## Reglas del proyecto
- [Convención de tipos, p.ej. TypeScript strict]
- [Manejo de errores]
- [Tests obligatorios o no]

## Comandos
- `[comando]` — [qué hace]
- `[comando]` — [qué hace]

## Decisiones arquitectónicas
- [Decisión + por qué se tomó]
```

**Truco:** Empieza simple. Hazlo crecer cuando Claude cometa un error que el `CLAUDE.md` debería haberle evitado.

---

### 3.7 Permissions — definir el "blast radius"

Permissions controla qué puede hacer Claude sin pedirte permiso. Es lo que separa "asistente cauto" de "asistente autónomo".

**Modos disponibles:**

| Modo | Comportamiento | Cuándo usarlo |
|---|---|---|
| `default` | Pregunta antes de modificar archivos o correr bash | Trabajo normal, código en producción |
| `acceptEdits` | Auto-aprueba ediciones de archivos; bash sigue pidiendo permiso | Iteración rápida, confías en el modelo |
| `plan` | Solo analiza y planea, **no modifica nada** | Antes de un cambio grande, revisión |
| `bypassPermissions` | Auto-aprueba TODO | Solo en sandboxes o CI |

**Reglas declarativas en `.claude/settings.json`:**

```json
{
  "permissions": {
    "allow": ["Bash(npm test)", "Bash(npm run lint)"],
    "deny": ["Bash(rm -rf*)", "Read(.env*)", "Bash(git push origin main)"],
    "ask": ["Bash(git push*)"]
  }
}
```

Orden de evaluación: **deny > ask > allow.**

---

### 3.8 Hooks — automatización determinista

A diferencia de los skills (sugerencias que el modelo puede o no seguir), los hooks son **scripts que se ejecutan siempre**, en momentos específicos del ciclo de vida.

**Eventos comunes:**
- `PreToolUse` — antes de ejecutar una herramienta (bloquear/modificar)
- `PostToolUse` — después de usar una herramienta (logging, validación)
- `Notification` — reenviar eventos a Slack, email, etc.

**Ejemplo — Formatear código automáticamente tras cada edit:**
```yaml
PostToolUse:
  - matcher: "Edit|Write"
    hooks:
      - type: command
        command: "npx prettier --write $CLAUDE_FILE_PATH"
```

**Ejemplo — Bloquear lectura de secrets:**
```yaml
PreToolUse:
  - matcher: "Read"
    hooks:
      - type: command
        command: "./scripts/block-secrets.sh"
```

> **Regla:** Si una regla de tu equipo es crítica (no leer `.env`, correr lint siempre), conviértela en hook. No la dejes en `CLAUDE.md` como advisory.

---

## Nivel Avanzado — Claude Code como herramienta seria

### 3.9 Subagents — especialistas con contexto aislado

Los subagents son "miembros del equipo" especializados. El agent principal puede delegarle tareas a un subagent que tiene contexto aislado, lo que evita saturar tu conversación principal.

**Definición típica** — archivo Markdown en `.claude/agents/security-reviewer.md`:

```markdown
---
name: security-reviewer
description: Revisor de seguridad. Úsalo después de cambios en auth o manejo de datos.
tools: Read, Grep, Glob, Bash
model: opus
permissionMode: plan
---

Eres un senior security engineer revisando código por vulnerabilidades.
Cuando te invoquen:
1. Identifica los archivos cambiados recientemente
2. Analiza por OWASP Top 10
3. Revisa secrets hardcoded, SQL injection, XSS
4. Reporta hallazgos con severidad y remediación
```

**Cuándo crear un subagent:**
- Tarea recurrente con instrucciones distintas al main agent (revisión de seguridad, migración de BD, generación de docs)
- Cuando quieres usar un modelo distinto (Opus para analysis, Haiku para tareas rutinarias)
- Para aislar contexto (que no "contamine" la sesión principal)

Más detalle de subagents en **Módulo 4**, ahí los organizamos por rol/seniority.

---

### 3.10 Flujos típicos de Claude Code

**Refactor seguro:**
```
1. /plan → Claude propone el refactor sin tocar nada
2. Revisas el plan, ajustas
3. Salir de plan mode → ejecuta el refactor
4. Hooks corren tests y linter automáticamente
5. Si fallan, Claude itera hasta arreglar
6. Tú revisas el diff y commiteas
```

**Debug de un test que falla:**
```
> El test "user.spec.ts > should create user with valid email" está fallando.
  Lee el test, el código que prueba, y dime qué está mal antes de modificar nada.
```

**Onboarding a un repo nuevo:**
```
> Lee la estructura completa del repo. Genera un CLAUDE.md inicial
  con: stack, comandos comunes, convenciones que detectes, y áreas
  donde sospechas deuda técnica. No modifiques nada más.
```

**Migración guiada:**
```
> Tengo que migrar de Pages Router (Next.js) a App Router.
  Crea un plan en 5 fases, identifica los riesgos por fase,
  y empezamos por la fase 1.
```

---

# Módulo 4 — Agentes: del C-Level al Analista

> Un **agente** es un proceso de Claude con instrucciones, herramientas y autonomía definidas para resolver un tipo específico de problema. Pueden ser tan simples como un Proyecto bien configurado (Módulo 2) o tan sofisticados como un subagent en Claude Code con MCP y hooks (Módulo 3).
>
> Este módulo no enseña sintaxis nueva — enseña **cuándo usarlos, cómo dirigirlos y quién hace qué** según tu rol en la organización.

---

## 4.1 El espectro de "agente"

Antes de hablar por rol, conviene entender que "agente" es un continuo, no una categoría binaria:

| Forma | Esfuerzo | Quién la crea | Ejemplo |
|---|---|---|---|
| **Personalizar (claude.ai)** | Minutos | Cualquier usuario | Instrucciones permanentes con tu nombre y tono |
| **Proyecto con instrucciones** | 30 min | Cualquier usuario | "Asistente de clientes" con briefing y docs |
| **Skill** | 1–2 horas | Power user / analista | Habilidad invocable con `/nombre-skill` |
| **Subagent (Claude Code)** | 2–4 horas | Desarrollador | Revisor de seguridad, migrador de DB |
| **Subagent + MCP + Hooks** | 1–2 días | Equipo técnico | Agente autónomo que opera infra real |
| **Agente custom con API** | Semanas | Equipo de ingeniería | Producto interno o externo |

Tu rol determina **en qué parte del espectro vives**, no si "haces agentes" o no.

---

## 4.2 C-Level (CEO, CFO, COO, CMO, CTO)

> **Tu trabajo con agentes: dirigir, no construir.**

El C-Level rara vez configura agentes con sus propias manos. Pero define qué problemas merecen un agente, aprueba el alcance/riesgo, y consume los outputs.

### Lo que un C-Level debería entender de agentes

1. **No son magia ni reemplazan juicio humano.** Son aceleradores de tareas con criterio definido.
2. **Tienen blast radius.** Un agente que puede mandar emails reales requiere más control que uno que solo redacta borradores.
3. **Necesitan instrucciones explícitas.** "Que ayude al equipo" no es un encargo, es un deseo.
4. **Sufren si el contexto está fragmentado.** Si tu información vive en 10 sistemas desconectados, los agentes serán mediocres hasta que conectes esas fuentes.

### Casos de uso C-Level

**CEO — Daily Executive Briefing**
- **Forma:** Proyecto en claude.ai con conectores a Gmail, Calendar y Drive
- **Instrucciones:** "Cada mañana sintetiza: emails relevantes de las últimas 24h, eventos del calendario, decisiones pendientes y señales de prensa/competencia que requieran mi atención. Formato: máximo 1 página, lenguaje directo, prioridades marcadas P0/P1/P2."
- **Output esperado:** 5 min de lectura, no 50 emails dispersos

**CFO — Monitor de KPIs y anomalías**
- **Forma:** Proyecto + skill custom que consume datos de tu BI (vía MCP)
- **Instrucciones:** "Compara KPIs semanales contra forecast. Alerta solo desviaciones >10%. Para cada alerta: causa más probable según contexto histórico + 1 acción sugerida."
- **Output esperado:** Te entera por excepción, no por reporte

**COO — Riesgos operativos**
- **Forma:** Proyecto con docs de SOPs y conector a Slack
- **Instrucciones:** "Detecta patrones en incidentes reportados en #ops-alerts. Si un tipo de incidente se repite >3 veces en 7 días, identifica el SOP afectado y propón actualización."

**CMO — Síntesis de campañas**
- **Forma:** Proyecto con conectores a Google Analytics y la herramienta de email marketing
- **Instrucciones:** "Cada lunes resume performance de campañas activas vs benchmark. Identifica 1 campaña que vale la pena escalar y 1 que conviene matar."

**CTO — Salud del equipo de ingeniería**
- **Forma:** Subagent en Claude Code con MCP de GitHub
- **Instrucciones:** "Analiza PRs abiertos hace >5 días, tiempo medio a review, cobertura de tests por módulo. Identifica cuellos de botella humanos sin nombrar personas."

### Qué decide el C-Level (no qué ejecuta)

```
□ ¿Este problema merece un agente o se resuelve con un proceso humano mejor?
□ ¿Qué herramientas reales puede tocar? (solo lectura / lectura + escritura / sin restricción)
□ ¿Quién es el dueño operativo del agente?
□ ¿Cómo medimos si funciona después de 30 días?
□ ¿Qué pasa si falla? ¿Quién se entera?
```

### Prompt típico para discusión con tu equipo técnico

```
Necesito que evalúen la viabilidad de un agente para:
[descripción del problema en lenguaje de negocio]

Quiero saber:
1. ¿Es factible con las herramientas actuales o requiere desarrollo?
2. ¿Qué información tendría que tener acceso?
3. ¿Cuál es el riesgo si toma una decisión equivocada?
4. ¿Cuánto tiempo de configuración y mantenimiento estimas?
5. ¿Qué proceso humano queda y cuál se automatiza?

Háganme una propuesta de 1 página antes de cualquier implementación.
```

---

## 4.3 Director / VP

> **Tu trabajo con agentes: definir el "qué" y conectar con procesos del área.**

El Director traduce la visión del C-Level en agentes operables. No los construye, pero define el alcance, las métricas y los handoffs con humanos.

### Casos de uso Director/VP

**Director de Operaciones — Reporting semanal automatizado**
- Crea un Proyecto compartido con su equipo
- Define las instrucciones del proyecto (qué se reporta, en qué formato, con qué tono)
- Su equipo de analistas conecta las fuentes de datos
- El agente produce el reporte; el director lo revisa antes de mandarlo

**VP de Ventas — Forecast de pipeline**
- Subagent en Claude Code (configurado por su Sales Ops Analyst)
- Consume datos del CRM vía MCP
- Outputs: probabilidad por deal, riesgos del trimestre, deals que requieren intervención
- El VP no toca el código, define la lógica de scoring y revisa weekly

**VP de Producto — Triage de feedback**
- Proyecto con conectores a Intercom, Slack y store reviews
- Instrucciones: "Clasifica cada pieza de feedback en: bug / feature request / confusion / praise. Identifica los 3 temas que crecieron esta semana."
- El VP lee solo el resumen y dirige al PM correcto

### Lo que define un Director

```
□ El alcance exacto del agente (qué SÍ hace, qué NO hace)
□ Las métricas de éxito a 30/60/90 días
□ Quién en su equipo es el dueño operativo
□ Cómo se integra en los procesos existentes (no agentes huérfanos)
□ Cómo escala: agente piloto → agente compartido → agente para toda la empresa
```

### Plantilla de briefing para tu equipo

```
PROYECTO DE AGENTE: [nombre]

PROBLEMA QUE RESUELVE
[1 párrafo en lenguaje de negocio, sin jerga técnica]

USUARIO PRINCIPAL
[Quién interactúa con él diariamente]

ALCANCE SÍ
- [Tarea 1]
- [Tarea 2]
- [Tarea 3]

ALCANCE NO
- [Lo que explícitamente queda fuera]

FUENTES DE DATOS REQUERIDAS
- [Sistema 1 — lectura/escritura]
- [Sistema 2 — lectura/escritura]

MÉTRICAS DE ÉXITO
- [Métrica 1] objetivo: [valor] en [plazo]
- [Métrica 2] objetivo: [valor] en [plazo]

DUEÑO OPERATIVO
[Persona del equipo]

PILOTO
- Duración: [X semanas]
- Usuarios piloto: [quiénes]
- Criterio para pasar a producción: [específico]
```

---

## 4.4 Manager / Team Lead

> **Tu trabajo con agentes: configurarlos para tu equipo y mantenerlos vivos.**

El Manager es quien convierte el briefing del Director en un agente funcional. Suele usar Proyectos compartidos y Skills, y a veces subagents de Claude Code si su equipo es técnico.

### Casos de uso Manager

**Manager de Marketing — Generador de borradores de contenido**
- Proyecto compartido con su equipo
- Instrucciones detalladas sobre voz de marca, formatos por canal, restricciones legales
- Documentos subidos: brand guidelines, ejemplos de contenido aprobado, glosario
- El equipo escribe prompts simples; el agente entrega borradores que el manager revisa

**Manager de Producto — Asistente de grooming**
- Proyecto con docs de discovery, OKRs del trimestre y archivo de decisiones pasadas
- Instrucciones: "Cuando reciba un request, evalúa: alineación con OKRs / esfuerzo estimado / dependencias / riesgo de no hacerlo. Marca con [DECIDIR] si requiere conversación humana."

**Manager de Customer Success — Plantillas de respuesta**
- Proyecto con casos resueltos anteriores, tono de marca y políticas
- Equipo lo usa para borradores de respuestas a tickets complejos
- Manager actualiza instrucciones cuando aparecen nuevos patrones

**Engineering Manager — Onboarding de nuevos devs**
- Subagent en Claude Code con CLAUDE.md detallado
- Documenta convenciones, comandos comunes, decisiones arquitectónicas
- Nuevos developers le hacen preguntas en lenguaje natural sin saturar al manager

### Lo que hace un Manager con agentes

```
□ Configurar instrucciones detalladas del proyecto/subagent
□ Mantenerlas al día (revisión mensual mínima)
□ Capacitar al equipo en cómo usarlo (3–4 sesiones cortas, no un manual)
□ Detectar cuándo el agente está fallando consistentemente y escalar al Director
□ Documentar las decisiones que el agente NO debe tomar
```

### Plantilla — Instrucciones de Proyecto compartido

```
[NOMBRE DEL PROYECTO] — CONTEXTO DEL EQUIPO

QUIÉN USA ESTE PROYECTO
- [Rol 1]: tareas típicas
- [Rol 2]: tareas típicas
- [Rol 3]: tareas típicas

CONVENCIONES DEL EQUIPO
- Tono: [específico]
- Formato por defecto: [específico]
- Idioma: [específico]

CONOCIMIENTO BASE
[Apuntas a los documentos subidos al proyecto]

DECISIONES YA TOMADAS (no las cuestiones)
- [Decisión 1] — razón
- [Decisión 2] — razón

CUÁNDO PEDIR ACLARACIÓN HUMANA
- Si te piden algo que afecta a [área sensible]
- Si las instrucciones se contradicen
- Si tienes <70% de confianza en el output

CÓMO RESPONDER
- Prioriza accionabilidad sobre exhaustividad
- Si algo requiere decisión humana, márcalo [REQUIERE DECISIÓN]
- Cita el documento de referencia cuando aplique
```

---

## 4.5 Analista / IC / Especialista

> **Tu trabajo con agentes: construirlos, conectarlos y mantenerlos.**

El analista o IC (Individual Contributor) es quien ensucia las manos. Configura subagents de Claude Code, crea Skills, conecta MCP servers, escribe hooks, y mantiene el `CLAUDE.md` del equipo.

### Casos de uso Analista

**Data Analyst — Subagent SQL especializado**
- Archivo `.claude/agents/sql-analyst.md` con conocimiento del schema del data warehouse
- Skill `/query-snowflake` para ejecutar consultas vía MCP
- Cuando el analista hace una pregunta de negocio, el subagent traduce a SQL, ejecuta, y devuelve resultado + interpretación

**Marketing Analyst — Generador de reportes de campaña**
- Skill `/reporte-campana` que toma como input el nombre de la campaña
- Lee datos de Google Analytics (MCP), de la plataforma de ads y del CRM
- Genera un reporte en Markdown con la estructura aprobada por el manager

**Sales Ops Analyst — Limpieza y enriquecimiento de leads**
- Subagent con acceso al CRM vía MCP
- Toma leads nuevos, los normaliza, los enriquece con datos públicos y los rutea según reglas

**Security Analyst — Triage de vulnerabilidades**
- Subagent `security-triage` que lee CVEs nuevos y los cruza contra las dependencias del repo
- Reporta solo los relevantes con severidad y plan de remediación

### Lo que hace un Analista con agentes

```
□ Escribir las definiciones de subagents en .claude/agents/
□ Configurar MCP servers (autenticación, scope, permissions)
□ Crear/mantener skills propias y del equipo
□ Definir hooks para automatización determinista
□ Mantener el CLAUDE.md del repo o del proyecto
□ Documentar para que el siguiente analista pueda heredar todo
```

### Estructura recomendada para un analista

```
proyecto/
├── CLAUDE.md                          # Contexto que Claude lee al iniciar
├── .claude/
│   ├── settings.json                  # Permissions, MCP servers, hooks
│   ├── agents/
│   │   ├── sql-analyst.md             # Tu subagent SQL
│   │   ├── report-generator.md        # Tu generador de reportes
│   │   └── data-quality.md            # Tu validador de datos
│   └── skills/
│       ├── query-snowflake/
│       ├── reporte-campana/
│       └── enriquecer-lead/
└── docs/
    └── agentes.md                     # Documentación de qué hace cada uno
```

### Plantilla — Subagent de un analista

```markdown
---
name: [nombre-corto-kebab-case]
description: [Cuándo invocarlo. Sé específico, esto se lee al decidir si usarlo]
tools: [Read, Grep, Bash(npm:*), MCP(snowflake:*)]
model: sonnet
permissionMode: default
---

# Rol

Eres [rol específico] con [contexto del dominio].

# Cuándo se te invoca

Te invocan cuando [trigger específico].

# Tu proceso

1. [Paso 1 — qué hacer primero]
2. [Paso 2 — cómo procesar]
3. [Paso 3 — qué entregar]

# Reglas duras

- NUNCA [acción prohibida]
- SIEMPRE [acción obligatoria]
- Si [condición ambigua] entonces [acción de seguridad]

# Formato de output

[Estructura exacta del output. Ejemplo concreto]

# Errores comunes que debes evitar

- [Error 1] — corrección: [qué hacer en su lugar]
- [Error 2] — corrección: [qué hacer en su lugar]
```

---

## 4.6 Matriz de implementación: rol × tipo de agente

| Tipo de agente | C-Level | Director | Manager | Analista |
|---|---|---|---|---|
| Personalizar (claude.ai) | Usa | Usa | Usa | Usa |
| Proyecto individual | Usa | Usa | Configura | Configura |
| Proyecto compartido | Aprueba alcance | Define alcance | **Configura** | Apoya |
| Skill | Consume output | Pide creación | Pide creación | **Crea** |
| Subagent Claude Code | Consume output | Aprueba alcance | Pide creación | **Crea y mantiene** |
| MCP server | Aprueba conexión | Aprueba conexión | Pide conexión | **Conecta y configura** |
| Hooks | — | — | Pide regla | **Implementa** |
| Agente custom con API | Aprueba inversión | Define caso | Coordina | **Co-construye con ingeniería** |

> **Negrita = es quien tiene la responsabilidad operativa principal.**

---

## 4.7 Anti-patrones por rol

**C-Level**
- Pedir "un agente que ayude al equipo" sin definir problema concreto
- Asumir que un agente reemplaza un proceso roto (lo amplifica)
- No definir blast radius hasta que algo sale mal

**Director**
- No definir métricas de éxito a 30/60/90 días
- Saltarse el piloto y desplegar a toda la organización
- Cambiar el alcance cada semana

**Manager**
- Instrucciones de Proyecto vagas ("usa buen criterio")
- No actualizar el agente cuando cambia la realidad operativa
- No capacitar al equipo en cómo usarlo

**Analista**
- Subagents sin documentación que solo entienden quien los creó
- Hooks que silenciosamente bloquean tareas legítimas
- MCP servers conectados sin definir permisos finos

---

## 4.8 Roadmap de adopción por organización

Para una empresa empezando con agentes, el orden recomendado:

```
Mes 1 — Personalizar + Proyectos personales
  → Cada persona aprende a usar Chat con contexto
  → No requiere ningún cambio organizacional

Mes 2 — Proyectos compartidos por equipo
  → 1 manager piloto por área
  → Mide tiempo ahorrado por persona

Mes 3 — Primeros Skills y subagents (analistas técnicos)
  → 2 o 3 casos de uso priorizados por dirección
  → Plan Pro o Team activado

Mes 4 — MCP y conectores con sistemas internos
  → Empieza con conectores de solo lectura
  → Define gobernanza: quién aprueba qué se conecta

Mes 5+ — Agentes con escritura, hooks, automatización determinista
  → Solo en procesos donde el costo de error está acotado
  → Auditoría continua
```

---

# Módulo 5 — Skills, MCP y Conectores

> Los agentes ganan superpoderes cuando pueden leer y escribir en sistemas externos. Esto se logra vía **Conectores** (en claude.ai) y **MCP** (Model Context Protocol, en Claude Code y planes superiores). Las **Skills** son habilidades empaquetadas que cualquier usuario puede invocar.

---

## 5.1 Conectores en claude.ai

Los conectores son integraciones nativas entre Claude y servicios populares. Se activan desde el campo de texto o en la configuración de tu cuenta.

**Conectores comunes disponibles:**

| Servicio | Qué puede leer/hacer |
|---|---|
| Gmail | Leer y resumir hilos, redactar respuestas, buscar |
| Google Calendar | Consultar disponibilidad, agendar, resumir agenda |
| Google Drive | Leer documentos, hojas, presentaciones |
| Figma | Leer diseños, generar componentes desde mockups |
| Canva | Crear y editar diseños desde texto |
| Vercel | Ver deployments, logs, estado de proyectos |
| Granola | Acceder a notas y transcripciones de reuniones |

**Cómo activarlos:**
1. Click en el ícono de herramientas en el campo de texto
2. Selecciona el conector
3. Autentícate la primera vez
4. Úsalo en lenguaje natural

**Ejemplo — Usando Gmail + Calendar:**
```
Revisa mis emails sin leer de las últimas 24 horas.
Identifica los 3 que requieren respuesta hoy.
Para cada uno, redacta un borrador de respuesta y propón un slot
de mi calendario si requieren reunión.
```

---

## 5.2 MCP (Model Context Protocol)

MCP es el protocolo abierto de Anthropic para que **cualquier servicio** pueda exponerse a Claude. Los conectores de claude.ai usan MCP por debajo, pero MCP también te permite conectar:

- Tu base de datos interna
- Herramientas internas de la empresa
- APIs públicas (CoinGecko, Stripe, Notion, etc.)
- Servidores propios que tú escribas

### Dónde se usa MCP

- En **Claude Code** vía `/mcp` (instalación manual o vía plugins)
- En **claude.ai** vía la sección de conectores (algunos MCP están preempaquetados)
- En **agentes custom** que construyas con la API

### Ejemplo — Conectar Supabase en Claude Code

```bash
# Instalar el MCP server de Supabase (vía plugin oficial)
claude /plugin install supabase

# Autenticarse
claude /mcp
> Supabase → Autenticar → [token]

# Usar
> Lista las últimas 10 filas de la tabla users.
> Crea una migración que agregue columna last_login a users.
```

### Crear tu propio MCP server

Si tienes una API interna que quieres exponer a Claude, puedes escribir tu propio MCP server. La especificación es abierta y hay SDKs en TypeScript, Python y otros lenguajes.

Ejemplo de capacidades típicas que expones:
- `query_db(sql)` — consultas a tu data warehouse
- `create_ticket(title, body)` — crear tickets en tu issue tracker
- `get_metrics(kpi, range)` — consultar métricas de negocio

> **Quién lo hace en una organización:** Los analistas técnicos o ingenieros (ver Módulo 4, sección 4.5). Los managers piden la integración, los directores aprueban el alcance.

---

## 5.3 Skills

Las **Skills** son habilidades empaquetadas que se invocan con `/nombre-skill`. Pueden venir built-in, instalarse desde marketplaces o crearse para uso interno.

**Tipos de Skills:**

| Tipo | Ejemplo | Quién la crea |
|---|---|---|
| Built-in (Claude Code) | `/init`, `/code-review`, `/security-review` | Anthropic |
| De plugin | `/figma-use`, `/figma-generate-design` | El proveedor del plugin |
| Personalizada | `/reporte-mensual`, `/onboarding-cliente` | Tu equipo |

**Cómo crear una skill (resumen):**

1. Crear directorio `skills/mi-skill/`
2. Escribir `skill.md` con instrucciones y argumentos
3. Configurar permisos si requiere acceso a herramientas
4. Probarla con `/mi-skill`

**Ejemplo — Skill `/reporte-campana`:**

```markdown
---
name: reporte-campana
description: Genera el reporte ejecutivo de performance de una campaña de marketing
arguments:
  - name: campana
    description: Nombre exacto de la campaña en GA4
    required: true
---

Genera un reporte de performance para la campaña: {{campana}}

Pasos:
1. Consulta GA4 (MCP) por las métricas de la campaña en los últimos 30 días
2. Compara contra el benchmark del trimestre
3. Identifica top 3 canales y bottom 3
4. Sugiere 1 acción concreta para escalar y 1 para optimizar

Formato: Markdown ejecutivo, máximo 1 página, con tabla resumen al inicio.
```

---

## 5.4 Gobernanza: quién aprueba qué se conecta

Cuando una organización abre conectores y MCP, conviene tener reglas claras:

| Decisión | Quién aprueba |
|---|---|
| Conectores personales (mi Gmail, mi Drive) | El usuario |
| Conectores con datos del equipo | Manager + IT |
| MCP con datos de clientes | Director + Compliance |
| MCP con escritura a sistemas críticos | C-Level + Compliance + Seguridad |

**Checklist antes de aprobar una nueva conexión:**

```
□ ¿Qué datos puede leer? ¿Hay PII o información regulada?
□ ¿Puede escribir? ¿Qué pasa si escribe mal?
□ ¿Quién es el dueño operativo si algo falla?
□ ¿Se puede limitar el scope (solo ciertas tablas, solo ciertos buckets)?
□ ¿Hay registro de qué hace cada vez que se invoca?
□ ¿Cómo se revoca el acceso si la persona deja la empresa?
```

---

# Módulo 6 — Flujos Combinados y Casos Reales

> Aquí aprendes a usar Chat + Proyectos + Claude Code + Agentes juntos para resolver problemas reales de principio a fin.

---

## Caso 1 — Lanzamiento de producto (equipo de marketing no técnico)

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

**Paso 4 — Artifact → formulario interactivo**
```
Crea un formulario HTML como artifact para la sección de registro.
Campos: nombre, email, empresa, cargo.
Botón: "Quiero acceso anticipado".
Estilo minimalista, fondo blanco, acento en azul marino.
```

**Paso 5 — Conector + Code Execution → análisis de resultados**
```
Conecta Google Analytics (MCP) y analiza los registros de la landing
de los primeros 15 días:
- Tasa de conversión por fuente de tráfico
- Perfil más común de quien se registra (cargo y empresa)
- Recomendación: ¿a cuál segmento enfocar los esfuerzos siguientes?
```

---

## Caso 2 — Informe ejecutivo para el board (Director con apoyo de analista)

**Situación:** Director que necesita transformar datos crudos en un reporte ejecutivo.

**Paso 1 — Analista en Claude Code → preparar el subagent**
El analista crea `.claude/agents/board-reporter.md` con la lógica de consolidación de datos y formato del reporte.

**Paso 2 — Subagent → consolidar y analizar**
```
> Invoca al board-reporter con los datos del Q3 que están en /data/q3/
```

**Paso 3 — Chat (Director) → narrativa ejecutiva**
```
Tengo estos resultados [pega los números].

Escribe la narrativa del reporte para el board:
3 párrafos — qué pasó, por qué importa, qué hacemos ahora.
Tono: directo, orientado a decisiones. Sin eufemismos ni relleno.
```

**Paso 4 — Artifact → presentación**
```
Convierte la narrativa + los datos en una presentación de 5 slides
como artifact. Slide por slide, con visualizaciones donde aplique.
```

---

## Caso 3 — Investigación de mercado completa (Emprendedor)

**Situación:** Emprendedor evaluando entrar a un nuevo sector.

**Paso 1 — Chat con búsqueda web → framework**
```
Voy a investigar el mercado de [sector] en [país].
Activa búsqueda web y dame el framework de análisis:
qué dimensiones cubrir, qué preguntas responder, y en qué orden.
```

**Paso 2 — Modo Research → síntesis profunda**
```
Usa el modo Research: investiga el mercado de [sector] en [país] cubriendo
las dimensiones que definimos. Quiero un reporte de 2 páginas con citas.
```

**Paso 3 — Proyecto → guardar el contexto del análisis**
Crea Proyecto "Mercado Sector X" y sube el reporte de Research como documento base. Todas las conversaciones futuras tendrán este contexto.

**Paso 4 — Code Execution → modelado de escenarios**
```
Dentro del Proyecto, en una nueva conversación:

Con base en los datos del reporte, crea una proyección financiera:
- Escenario conservador: 2% de captura de mercado
- Escenario base: 5%
- Escenario optimista: 10%

Para cada uno: ingresos proyectados año 1, 2 y 3
asumiendo precio de venta de $X y costo promedio de $Y.
Muéstrame la tabla, el código Python y un gráfico.
```

---

## Caso 4 — Equipo de ingeniería implementando feature (todos los módulos)

**Situación:** Equipo de 3 devs construyendo una nueva feature.

**Paso 1 — Engineering Manager → spec con claude.ai**
Proyecto compartido del equipo con docs de arquitectura. El manager redacta el spec funcional con Claude.

**Paso 2 — Tech Lead → diseño técnico en Claude Code**
```
> /plan
> Lee el spec en docs/specs/feature-X.md y el código de la app.
  Propón diseño técnico: archivos a tocar, cambios de schema, riesgos.
```

**Paso 3 — Devs → implementación con Claude Code**
Cada dev usa Claude Code en su rama. Hooks corren tests y linter automáticamente.

**Paso 4 — Code Review subagent → revisión antes del PR**
```
> /code-review
```

**Paso 5 — Security Review subagent → revisión de seguridad**
```
> /security-review
```

**Paso 6 — Manager → release notes con claude.ai**
Vuelve al proyecto compartido, le pasa el diff y le pide release notes en lenguaje de producto.

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
| Crear artifact | "Crea esto como artifact para poder editarlo" |
| Activar web | (botón en campo de texto) "Busca fuentes recientes para X" |

### Proyectos
| Necesidad | Acción |
|---|---|
| Crear contexto base | Instrucciones del proyecto (briefing completo) |
| Agregar conocimiento | Subir documentos al proyecto |
| Separar temas | Una conversación por tema |
| Actualizar contexto | Editar instrucciones cuando cambien los datos |
| Colaborar en equipo | Compartir el proyecto (Plan Pro / Team) |

### Claude Code
| Necesidad | Comando |
|---|---|
| Iniciar | `claude` en la raíz del proyecto |
| Ver/editar memoria | `/memory` |
| Generar CLAUDE.md inicial | `/init` |
| Configurar agentes | `/agents` |
| Configurar hooks | `/hooks` |
| Configurar permisos | `/permissions` |
| Gestionar MCP | `/mcp` |
| Gestionar plugins | `/plugin` |
| Modo plan (no modifica) | `/plan` |
| Code review | `/code-review` |
| Security review | `/security-review` |

### Agentes
| Rol | Lo que sí haces | Lo que no haces |
|---|---|---|
| C-Level | Decidir qué problemas merecen agente, aprobar blast radius | Configurar agentes con tus manos |
| Director | Definir alcance, métricas, handoffs | Escribir las instrucciones técnicas |
| Manager | Configurar Proyectos compartidos, mantener instrucciones | Escribir subagents en código |
| Analista | Crear subagents, skills, MCP, hooks; documentar todo | Tomar decisiones de alcance estratégico solo |

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

Claude Code:
□ ¿Tengo CLAUDE.md con stack, comandos y convenciones?
□ ¿Configuré permissions para evitar acciones peligrosas?
□ ¿Definí hooks para reglas críticas?
□ ¿Tengo subagents para tareas recurrentes?

Agentes:
□ ¿El alcance está escrito y aprobado por su nivel correspondiente?
□ ¿Hay métricas de éxito a 30/60/90 días?
□ ¿Está claro quién es el dueño operativo?
□ ¿El blast radius es proporcional a la criticidad?
```

---

## Glosario rápido

| Término | Qué es |
|---|---|
| **Artifact** | Documento o código generado por Claude en panel lateral, editable y reutilizable |
| **Proyecto** | Espacio de trabajo en claude.ai con instrucciones y documentos persistentes |
| **Claude Code** | Herramienta CLI/IDE para desarrollo con Claude |
| **CLAUDE.md** | Archivo de contexto que Claude Code lee al iniciar cada sesión |
| **Subagent** | Agente especializado dentro de Claude Code con system prompt y tools propios |
| **Skill** | Habilidad invocable con `/nombre-skill` |
| **Hook** | Script que se ejecuta automáticamente en eventos del ciclo de vida (determinista) |
| **MCP** | Model Context Protocol — protocolo para conectar Claude con servicios externos |
| **Conector** | Integración nativa entre claude.ai y un servicio (Gmail, Drive, Figma, etc.) |
| **Permission mode** | Configuración de cuánto puede hacer Claude sin pedir confirmación |
| **Extended Thinking** | Modo de razonamiento profundo activable en algunos modelos |

---

## Referencias y siguiente paso

- **Documentación oficial:** docs.anthropic.com
- **Guía del menú Customize de Claude Code:** ver archivo `claude-code-customize-guia.md` en esta carpeta
- **Material de marketing del curso:** ver archivo `marketing_publicaciones.md` en esta carpeta

> Este curso es un punto de partida. Cada módulo se puede profundizar — pero con lo cubierto aquí tienes todo lo necesario para usar Claude productivamente desde el día 1, sin importar tu rol.
