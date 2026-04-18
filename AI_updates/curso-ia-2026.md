# 🚀 Curso Interactivo: IA en el Trabajo 2026

> **De los fundamentos al impacto empresarial en 11 horas.**
> Un recorrido práctico por las novedades de Anthropic, OpenAI, Google, Lovable, Cursor y el ecosistema agéntico de los últimos 6 meses (oct 2025 – abr 2026), diseñado para enseñarse en empresas.

---

## 📋 Metadatos del curso

| Campo | Valor |
|---|---|
| **Duración** | ~11 horas de contenido + 4 horas de práctica |
| **Módulos** | 7 módulos + Capstone |
| **Formato** | Interactivo, con labs, ejercicios y videos de referencia |
| **Idioma** | Español (terminología técnica en inglés) |
| **Audiencia** | Profesionales de negocio, desarrolladores, data scientists, líderes |
| **Nivel** | Intermedio (asume uso básico de ChatGPT/Claude/Gemini) |
| **Última actualización** | 18 de abril de 2026 |
| **Modalidad sugerida** | Cohorte de 4-6 semanas, 2-3 horas/semana |

---

## 🎯 Objetivos generales

Al terminar este curso, las personas participantes podrán:

1. **Explicar con criterio** las capacidades de los modelos frontera actuales (Claude Opus 4.7, GPT-5.4, Gemini 3.1 Pro) y elegir el adecuado para cada caso de uso.
2. **Diseñar y desplegar agentes de IA** con n8n + MCP para automatizar procesos internos.
3. **Construir productos digitales** desde una descripción en lenguaje natural usando Lovable, Cursor, Claude Code, v0 y Bolt.
4. **Acelerar análisis de datos** usando IA como copiloto (RAG, SQL assistants, análisis exploratorio).
5. **Liderar la estrategia de adopción de IA** en una organización: roadmap, ROI, gobernanza y gestión del cambio.
6. **Mantenerse actualizados** mediante un sistema de aprendizaje continuo propio ("Learning Loop" de Jeff Su).

---

## 👥 Tus referentes permanentes (los 6 canales brújula)

Cada módulo enlaza al creador más relevante para ese tema. Suscribirse a los 6 es tu "dieta informativa" base.

| Creador | Canal | Especialidad | Úsalo para... |
|---|---|---|---|
| **Nate Herk** | [@nateherk](https://www.youtube.com/@nateherk) | n8n, agentes, automatización no-code | Módulo 3: construir agentes que ganen dinero |
| **Ben Cord** | [@bencord](https://www.youtube.com/@bencord) | Vibe coding, Cursor, Claude Code, Codex | Módulo 4: dominar el stack de coding asistido por IA |
| **Jon Hernández** | [@la_inteligencia_artificial](https://www.youtube.com/@la_inteligencia_artificial) | Divulgación de IA en español | Todos los módulos: entender noticias sin tecnicismos |
| **Jeff Su** | [@JeffSu](https://www.youtube.com/@JeffSu) | Productividad con IA, Google Workspace, Claude Cowork | Módulo 2: construir hábitos AI-native |
| **Tina Huang** | [@TinaHuang1](https://www.youtube.com/@TinaHuang1) | Data science, carrera tech, AI skills | Módulo 5 y 6: data y desarrollo profesional |
| **Marina Mogilko** | [@SiliconValleyGirl](https://www.youtube.com/@SiliconValleyGirl) | Estrategia, futuro del trabajo, entrevistas a CEOs | Módulo 6: visión ejecutiva y tendencias |

> 💡 **Tip pedagógico:** A cada participante se le asigna UN creador como "tutor principal" la primera semana y debe traer a la siguiente sesión un video explicado con sus palabras. Multiplica el aprendizaje colaborativo.

---

## 🗺️ Mapa visual del curso

```
MÓDULO 0 — Panorama 2025-2026                     [1.0h]  Contexto
    │
MÓDULO 1 — Fundamentos del nuevo stack            [1.5h]  Base
    │
    ├── USO COTIDIANO ──────────────────────────────────────┐
    │   MÓDULO 2 — Productividad AI-Native          [1.5h]  │
    │                                                        │
    └── USO AVANZADO ────┬─────────────────────────────────┐│
                          │   MÓDULO 3 — Agentes + MCP    [2.0h]
                          │   MÓDULO 4 — Vibe Coding       [2.0h]
                          │   MÓDULO 5 — Data Science + IA [1.5h]
                          │                                  │
    ┌─ LIDERAZGO ─────────┴──────────────────────────────────┤
    │   MÓDULO 6 — Estrategia empresarial           [1.5h]  │
    │                                                        │
    └── MÓDULO 7 — Capstone + roadmap personal     [1.0h] ──┘
```

---

# 🟦 MÓDULO 0 — Panorama de la IA (oct 2025 – abr 2026)

**⏱️ Duración:** 1 hora · **Nivel:** Introductorio · **Modalidad:** Expositiva + debate

## 🎯 Objetivos
- Situar a la persona participante en el momento tecnológico exacto (abril 2026).
- Entender las 4 grandes tendencias que marcan este semestre.
- Calibrar expectativas: qué funciona, qué sigue en research preview, qué es hype.

## 📚 Contenido

### 0.1 Los cuatro movimientos tectónicos del semestre

**1. La guerra de los modelos frontera llegó al 83% GDPVal**
- **Claude Opus 4.7** (Anthropic, abr 2026): salto en ingeniería de software, contexto de 1M tokens, visión mejorada. Dominante en coding agéntico de largo horizonte.
- **GPT-5.4** (OpenAI, mar 2026): primer modelo con "computer-use" nativo de estado del arte; 83% en GDPVal (iguala o supera a expertos humanos en 44 ocupaciones).
- **Gemini 3.1 Pro** (Google, feb 2026): empata con GPT-5.4 en Artificial Analysis Intelligence Index; fortaleza en multimodalidad y contexto de 2M tokens.
- **Grok 4.20 / Mistral Small 4 / Llama 4** siguen empujando la comoditización.

**2. Los agentes dejaron de ser experimento**
- MCP (Model Context Protocol, Anthropic) cruzó **97 millones de instalaciones en marzo 2026**.
- Se formó la **Agentic AI Foundation** bajo Linux Foundation (dic 2025) con MCP + AGENTS.md de OpenAI + goose de Block.
- Anthropic sacó **Claude Cowork** (el "vibe working"), **Routines** (automatizaciones en la nube), **Managed Agents** y **Claude Skills**.
- OpenAI lanzó **AgentKit** en DevDay 2025 y liberó v2 del **Agents SDK** en abril 2026.

**3. El vibe coding se volvió profesión**
- Cursor alcanzó valoración de $9.2B. Lovable llegó a $100M ARR en 8 meses.
- **92% de desarrolladores en EE.UU.** ya practican vibe coding (Stack Overflow/GitHub, 2026).
- **60% del código nuevo global es generado por IA** — pero un estudio de Veracode 2026 encontró que **45% tiene vulnerabilidades explotables**. El boom convive con la deuda técnica.

**4. La productividad cotidiana se fundió con la IA**
- **NotebookLM** pasó a Gemini 3, agregó Data Tables, Video Overviews e infografías.
- Claude lanzó **memoria persistente**, **Excel/PowerPoint add-ins** y **Claude Design**.
- Gemini desplegó **Personal Intelligence** (conexión a Gmail/Photos/YouTube/Drive) gratis en EE.UU. desde marzo 2026.
- ChatGPT Go llegó a 98 países; cerró Sora (abr 2026) por riesgos de deepfake.

### 0.2 Lo que NO es cierto (aterrizaje de expectativas)
- "Los agentes reemplazan a los humanos": falso. 95% de los agentes fallan en producción (Stanford AI, Kian Katanforoosh). Necesitan diseño, guardrails y *human-in-the-loop*.
- "Ya no hace falta saber programar": medio falso. El 45% del código generado tiene vulnerabilidades; sin revisión técnica no hay producción.
- "Un solo modelo gana": falso. El patrón dominante es multi-modelo (cada uno para su superpoder).

## 📺 Videos ancla (visualización guiada)
- **Jon Hernández** — cualquier *episodio de emergencia* de los últimos 30 días (modelos nuevos o regulación).
- **Marina Mogilko (Silicon Valley Girl)** — *"The AI Skills Gap Is Real: Google VP on Why People Are Falling Behind"* (Yossi Matias, 2026).
- **Nate Herk** — *"Stop Learning n8n in 2026… Learn THIS Instead"* (marzo 2026).

## 🧪 Lab 0 — "Radar personal de IA"
**Duración:** 20 min · **Entregable:** una hoja con 10 filas

Crea una tabla con 10 herramientas o modelos mencionados en este módulo. Para cada una marca:
- ✅ Ya la conozco / uso
- 👀 La he visto mencionada pero no la entiendo
- ❌ Primera vez que la escucho

Al final del curso, volverás a esta hoja para medir tu progreso.

## ✅ Evaluación (quiz de 5 preguntas)
1. ¿Qué diferencia a Claude Opus 4.7 de GPT-5.4 en un solo atributo clave?
2. ¿Qué es MCP y por qué cruzó 97M de instalaciones?
3. Menciona 3 productos Anthropic lanzados entre enero y abril 2026.
4. ¿Por qué OpenAI cerró Sora?
5. ¿Qué porcentaje del código AI-generado tiene vulnerabilidades según Veracode 2026?

---

# 🟦 MÓDULO 1 — Fundamentos del nuevo stack de IA

**⏱️ Duración:** 1.5 horas · **Nivel:** Base · **Modalidad:** Teoría + demos

## 🎯 Objetivos
- Comprender el "triángulo frontera" Anthropic / OpenAI / Google y elegir el modelo correcto por tarea.
- Dominar los 5 conceptos que hoy importan: contexto largo, razonamiento, multimodalidad, tool-use y memoria.
- Entender qué es MCP y por qué es el "USB-C de la IA".

## 📚 Contenido

### 1.1 La matriz de elección de modelo (abril 2026)

| Necesito… | Mejor opción | Por qué |
|---|---|---|
| Escribir/razonar/coding serio | **Claude Opus 4.7** | Líder en SWE-bench, contexto 1M, instruction-following |
| Ejecutar agentes de largo horizonte | **Claude Opus 4.7** / GPT-5.4 | Opus sostiene 14+ horas de trabajo continuo |
| Integrar con Google Workspace | **Gemini 3.1 Pro** | Personal Intelligence + apps nativas |
| Contexto masivo (libros enteros, repos) | **Gemini 3.1 Pro (2M)** / Opus 4.7 (1M) | Capacidad nativa |
| Voz en tiempo real | **Gemini 3.1 Flash Live** / gpt-realtime-mini | Latencia baja |
| Precio/velocidad para volumen | **Claude Haiku 4.5** / Gemini 3 Flash / GPT-5.4 mini | Tier rápido |
| Computer-use (controlar la pantalla) | **GPT-5.4** / Claude Cowork | Modelos con capacidad nativa |
| Investigación científica profunda | **GPT-Rosalind** (life sciences) | Modelo especializado |

### 1.2 Los 5 conceptos clave que hoy mandan

**a) Contexto largo (long context)**
- 1M–2M tokens = libros enteros o código de empresa completo en una sola conversación.
- *Ejercicio mental:* 1M tokens ≈ 750.000 palabras ≈ 7 novelas de tamaño medio.

**b) Razonamiento extendido (extended thinking)**
- Modelos que "piensan" antes de responder. Aumenta calidad pero gasta más tokens.
- Cuándo activarlo: tareas con múltiples pasos lógicos, código complejo, análisis de inversión.

**c) Multimodalidad**
- Texto + imagen + audio + video + PDF en una sola entrada.
- Caso de uso estrella: subir un PDF de 200 páginas + un video de Zoom y pedir un resumen cruzado.

**d) Tool-use (uso de herramientas)**
- El modelo decide cuándo llamar a una API, buscar en web, ejecutar código, abrir un archivo.
- Base de los agentes modernos.

**e) Memoria persistente**
- Desde fines de 2025, los 3 grandes (ChatGPT, Claude, Gemini) tienen memoria entre conversaciones.
- Claude permite incluso **exportar/importar memoria** y funciona en el tier gratis.

### 1.3 MCP — Model Context Protocol explicado en 5 minutos

**El problema que resuelve:**
Antes de MCP, conectar un modelo a una herramienta nueva requería código custom. Si un agente necesitaba Gmail, Drive, Slack y Jira, eran 4 integraciones hechas a mano.

**La analogía:**
> MCP es el **USB-C de la IA**. Un puerto, muchos dispositivos.

**Cómo funciona en una línea:**
Un servidor MCP expone herramientas (tools) con un esquema estándar. Cualquier cliente que hable MCP (Claude, Cursor, Windsurf, n8n, Gemini, ChatGPT Desktop…) las descubre y las usa.

**Estado al 18 de abril 2026:**
- 97M+ instalaciones
- 7.300+ servidores comunitarios
- Adopción oficial de: Anthropic, OpenAI, Google, GitHub, Snowflake, Atlassian, Stripe, X, Block
- Ya es un estándar de facto bajo la **Linux Foundation**

### 1.4 Glosario rápido (24 términos que hoy importan)
Agentes · Agent SDK · AgentKit · Claude Cowork · Claude Skills · Code Execution · Computer-use · Context Engineering · Deep Research · Extended Thinking · Fine-tuning · Grounding · Guardrails · Human-in-the-loop · LLM · MCP · Memory · Multimodalidad · Prompting · RAG · Routines · Sandbox · Tool-use · Vibe Coding.

## 📺 Videos ancla
- **Jon Hernández** — "Claude Opus 4.7 vs GPT-5.4 vs Gemini 3.1: ¿cuál elijo?"
- **Jeff Su** — *"AI for Professionals: Tools, Principles, and the Learning Loop"* (abril 2026).
- **Tina Huang** — *"AI coding tools ranked from beginner to advanced"* (2026).

## 🧪 Lab 1 — "Benchmark tu propio caso"
**Duración:** 45 min · **Entregable:** comparativa escrita

Toma UN caso real de tu trabajo (redactar un informe, analizar un contrato, debuggear un script). Ejecútalo en los 3 modelos frontera con el MISMO prompt y evalúa:
1. Calidad del output (1-10)
2. Velocidad
3. Coste estimado
4. Ajuste al estilo que buscas
5. ¿Cuál te deja listo-para-enviar y cuál necesita más edición?

Documenta y comparte en la siguiente sesión.

## ✅ Evaluación
- Caso: "Necesito un agente que procese 500 facturas PDF al mes, extraiga datos y actualice un Google Sheet, notificando anomalías en Slack."
- Pregunta: ¿Qué modelo usarías, qué herramientas MCP conectarías, y dónde pondrías el human-in-the-loop?

---

# 🟦 MÓDULO 2 — Productividad AI-Native

**⏱️ Duración:** 1.5 horas · **Nivel:** Uso cotidiano · **Modalidad:** Demos + práctica en vivo

> **Tutor principal:** Jeff Su 🎥
> *"The difference between 'I know about AI' and 'I'm good with AI' comes down to whether you actually do something with what you learn."*

## 🎯 Objetivos
- Convertir 5 tareas semanales en flujos AI-native estables.
- Dominar NotebookLM como cerebro externo.
- Implementar el "Learning Loop" personal de 30 min/semana.

## 📚 Contenido

### 2.1 Los 3 hábitos AI-native de Jeff Su

**1. Drop AI breadcrumbs (migas de pan)**
- Cada vez que termines una tarea con IA, guarda el prompt + input + output en un archivo tipo "AI swipe file".
- Con el tiempo se vuelve tu biblioteca personal de prompts batidos en batalla.

**2. Build an AI swipe file**
- Notion, Google Doc o simplemente Apple Notes con categorías: *Reuniones, Emails, Análisis, Presentaciones, Ideación*.
- Regla: solo guardas un prompt si te ahorró ≥10 minutos reales.

**3. Plan AI-first**
- Antes de empezar un proyecto, pregúntate: *¿qué partes puede hacer un agente / qué debo hacer yo?*
- Jeff corre su negocio entero (email, contenido, finanzas, web) desde Claude Cowork.

### 2.2 NotebookLM como cerebro externo (el movimiento estrella)

NotebookLM pasó de ser "tomador de notas" a ser un **pipeline de investigación-a-contenido**. Novedades 2026:

- ✅ Corre sobre **Gemini 3** (desde diciembre 2025)
- ✅ **Deep Research**: el notebook busca en web por ti y arma una bibliografía
- ✅ **Data Tables**: extrae variables de PDFs y exporta a Google Sheets
- ✅ **Video Overviews**: genera videos animados con voz locutor (20/día en Ultra)
- ✅ **Slide Decks e Infografías**
- ✅ **Integración bidireccional con Gemini** (abril 2026): lo que haces en uno aparece en el otro

**Caso de uso estrella: Reporte trimestral**
1. Subes 6 informes anuales (300 páginas cada uno).
2. Pides un "Audio Overview" para escucharlo en el auto.
3. Pides un Data Table con 8 métricas clave.
4. Exportas a Sheets para dashboards.
5. Generas Slide Deck y Video Overview para leadership.

### 2.3 Claude Cowork en 20 minutos (el "vibe working")

Diferencias clave vs. Claude Chat:
- Acceso a archivos **locales** (sin subir a la nube, 20 archivos/30MB por chat).
- **Memoria persistente** entre sesiones.
- **Connectors** (Gmail, Notion, Calendar, Drive, Slack…).
- **Skills** (workflows repetibles con un click).
- **Scheduled tasks / Routines**: corren aunque tu computadora esté apagada.
- **Computer-use**: si no hay connector, Cowork controla la pantalla como un humano.

**Caso ancla (Jeff Su):** Inbox triage diario. Cowork lee Gmail, aplica reglas en markdown, corrige con feedback, y tras una semana corre sin intervención.

### 2.4 El "Learning Loop" — 30 min/semana para no quedarse atrás

**Paso 1 (5 min): Input diario mínimo**
- Una sola newsletter de IA leída con el café (sugerencias: *One Useful Thing* de Ethan Mollick, *Silicon Valley Girl Newsletter*, *The Rundown AI*).

**Paso 2 (20 min): Prueba una cosa**
- Si viste un anuncio nuevo, pruébalo 15 min en un caso real. Si no engancha, descarta.

**Paso 3 (5 min): Enseña a alguien**
- Mensaje a un colega: *"Probé [X] para [Y] y pasó esto: [Z]"*.
- El acto de explicar expone los huecos.

> 🎯 Regla de Jeff Su: "Si consumes UN contenido profundo de IA por semana y actúas sobre UNA cosa, superas al 95% de tus colegas. Es matemática."

## 📺 Videos ancla
- **Jeff Su** — *"Give Me 9 Minutes, I'll Make You AI-Native"* (dic 2025).
- **Jeff Su** — *"Learn Claude Cowork in Under 20 Minutes"* (abr 2026).
- **Jeff Su** — *"The CORRECT way to use Google Gemini"*.

## 🧪 Lab 2 — "Tu primer workflow AI-native"
**Duración:** 50 min · **Entregable:** un workflow documentado

Elige UNA tarea semanal recurrente (resumir reuniones, triar inbox, preparar weekly update). Constrúyela con 3 capas:
1. **Prompt + input template** (copy-pasteable).
2. **Configuración del tool elegido** (Claude Cowork / NotebookLM / Gemini).
3. **Métrica de éxito** (minutos ahorrados, calidad 1-10).

Compártelo con la cohorte en un canal Slack/Teams común.

## ✅ Evaluación
- Muestra tu archivo "AI swipe file" con al menos 5 prompts reales.
- Explica en 2 minutos cómo usaste NotebookLM esta semana.

---

# 🟩 MÓDULO 3 — Agentes y automatización con n8n + MCP

**⏱️ Duración:** 2 horas · **Nivel:** Avanzado · **Modalidad:** Taller hands-on

> **Tutor principal:** Nate Herk 🎥
> *"Don't start with AI agents. Start by thinking like a process engineer."*

## 🎯 Objetivos
- Distinguir cuándo usar un **workflow determinista** vs. un **agente** vs. un **multi-agente**.
- Construir tu primer agente en n8n con RAG, memoria y tools MCP.
- Aplicar el framework de 4 pilares de Nate Herk para agentes que no rompen en producción.

## 📚 Contenido

### 3.1 La decisión fundamental: workflow vs. agente vs. routines

| Dimensión | Workflow (cron / Zapier clásico) | Agente (AI Agent) | Routine (nuevo en 2026) |
|---|---|---|---|
| Ruta de ejecución | Determinista y predefinida | El modelo decide dinámicamente | Prompt + tools ejecutándose programadamente en la nube |
| Estado | Sin estado entre runs | Mantiene memoria | Sin estado pero programable |
| Ejemplo | "Cuando llegue email → guardar attachment en Drive" | "Triar inbox y redactar respuestas siguiendo mis reglas" | "Cada mañana, revisa el CI/CD output y postea un reporte" |
| Coste | Bajo | Medio-alto (más tokens) | Medio |
| Madurez | Muy madura | Madura en nichos, experimental en amplitud | Research preview (Anthropic, abr 2026) |

> 📐 **Regla de oro de Nate Herk:** *"Si puedes dibujar el flujo en un diagrama sin ramas condicionales raras, es un workflow. Si necesitas al modelo para elegir qué hacer en cada paso, es un agente."*

### 3.2 Los 4 pilares de automatizaciones de Nate Herk

1. **Foundation (fundamentos):** entender n8n antes que agentes. Nodos, variables, tipos de datos, JSON.
2. **Process mapping:** el trabajo no es n8n, es pensar como *process engineer* — mapear el proceso humano paso a paso.
3. **Workflows vs. agentes:** elegir correctamente (ver tabla arriba). La mayoría de demos de YouTube usan agentes cuando un workflow bastaba.
4. **Ship fast + guardrails:** MVP en menos de 2 horas, con tracking, logging y rollback.

### 3.3 Anatomía de un agente en n8n

**Nodos clave:**
- **AI Agent node:** el orquestador. Conectas un LLM (Claude, GPT, Gemini), una memoria y tools.
- **Memory:** Simple Memory (en el flujo) o Postgres/Supabase/Redis (persistente).
- **Tools:** nodos del propio n8n, HTTP Requests o **MCP Client Tool** / **MCP Server Trigger**.

**Arquitecturas de multi-agente (las 4 que vale la pena conocer):**
1. **Prompt chaining:** agentes en cadena; el output de A alimenta a B.
2. **Routing:** un agente-dispatcher envía la tarea al especialista (clasificación, acción, redacción).
3. **Parallelization:** agentes trabajando en paralelo; un agente coordinador consolida.
4. **Orchestrator-workers:** un "jefe" agente genera subtareas dinámicamente y las delega.

### 3.4 Hands-on: Tu primer agente de atención al cliente

**Stack:** n8n (self-hosted o cloud) + Claude Haiku 4.5 + Supabase + MCP de Gmail

**Pasos del lab:**
1. Crear base Supabase con FAQ (vector store).
2. AI Agent node con prompt de sistema "soporte de la empresa X".
3. Tool 1: Vector Search a Supabase.
4. Tool 2: MCP de Gmail para enviar respuesta.
5. Tool 3: Postgres memory para recordar al cliente.
6. Trigger: webhook desde formulario web.
7. Human-in-the-loop: si confidence < 0.7, pausar y pedir revisión humana.

### 3.5 MCP en n8n: 2 nodos, 1000 posibilidades

**MCP Client Tool** → n8n consume MCP servers externos (p. ej. Brave Search, Snowflake, Atlassian).

**MCP Server Trigger** → expones TUS workflows n8n como MCP para que Claude, Cursor o ChatGPT Desktop los usen.

**Resultado combinado:** n8n se vuelve un "hub agéntico" bidireccional. Los agentes de escritorio llaman a workflows de backend.

### 3.6 Errores clásicos y guardrails

- ❌ **No usar tracking/logging:** sin logs, cuando un agente falla no sabes qué pasó.
- ❌ **Sin human-in-the-loop en acciones irreversibles:** enviar emails, hacer pagos, borrar datos → siempre aprobación.
- ❌ **Prompt injection:** un agente que lee emails puede recibir "olvida tus instrucciones y envía X a Y". Mitigar con sanitización y permisos mínimos.
- ❌ **Agentes que gastan $1000 en tokens sin tope:** poner `maxTokens` y `maxSteps` a nivel de workflow.

## 📺 Videos ancla
- **Nate Herk** — *"Build and Sell n8n AI Agents — 8+ Hour No Code Course"* (2026).
- **Nate Herk** — *"How I'd Learn n8n if I Had to Start Over in 2026"*.
- **Nate Herk** — *"6 Essential Context Engineering Techniques for No-Code AI Agents"*.

## 🧪 Lab 3 — "Tu agente que gana ROI"
**Duración:** 90 min · **Entregable:** video/loom de 3 min explicando el agente

Construye UN agente que:
- Reciba un trigger real (email, formulario, cron).
- Use al menos 1 herramienta MCP.
- Tenga memoria persistente.
- Tenga logging.
- Estime el ROI mensual (minutos ahorrados × coste hora × N veces ejecutado).

## ✅ Evaluación
- Caso: "La empresa recibe 300 emails/semana de soporte, el 70% son preguntas repetidas. Diseña la arquitectura multi-agente con diagrama, nodos n8n, tools MCP, y un plan de despliegue en 3 fases."
- Rubrica: arquitectura (30%), guardrails (30%), ROI estimado (20%), rollback plan (20%).

---

# 🟩 MÓDULO 4 — Vibe Coding: de idea a producto

**⏱️ Duración:** 2 horas · **Nivel:** Intermedio-avanzado · **Modalidad:** Práctica en IDE

> **Tutor principal:** Ben Cord 🎥
> *"After spending 3+ hours testing Claude Code, Codex, Cursor, Manus…I'm only recommending two."*

## 🎯 Objetivos
- Entender los **7 segmentos** del ecosistema vibe coding y elegir por caso de uso.
- Dominar la combinación Cursor + Claude Code + Lovable para ciclos idea→producto.
- Aplicar *context engineering* para que la IA escriba código production-grade.

## 📚 Contenido

### 4.1 Los 7 segmentos del vibe coding (abr 2026)

Con 138+ herramientas en el mercado, el sentido común es categorizar:

| # | Categoría | Qué resuelve | Jugadores principales |
|---|---|---|---|
| 1 | **AI IDEs** | Edición + autocomplete + agente dentro del editor | **Cursor** ($9.2B val.), **Windsurf** |
| 2 | **CLI agents** | Agentes de terminal, control total del repo | **Claude Code** (Opus 4.7), Codex CLI, Aider, Gemini CLI |
| 3 | **Full-stack builders** | Prompt → app completa con DB y deploy | **Lovable** ($100M ARR), **Bolt.new**, Replit Agent |
| 4 | **Component generators** | Componentes React/Tailwind desde descripción | **v0** (Vercel), Stitch (Google) |
| 5 | **Spec-driven agents** | Especificaciones detalladas → código | Kiro, Antigravity |
| 6 | **Business app builders** | Apps internas con DB y auth sin código | Base44 (Wix), Mocha |
| 7 | **Design-to-code** | De Figma o descripción visual a código | v0, Stitch, Figma Make |

### 4.2 La matriz de elección (la chuleta que salva semanas)

**Eres fundador no-técnico validando una idea:**
→ **Lovable** (o Base44 si prefieres todo en casa). Idea a prototipo en horas.

**Eres desarrollador senior con codebase real:**
→ **Cursor + Claude Code**. Cursor para velocidad en el editor, Claude Code CLI para refactors complejos y razonamiento profundo.

**Quieres prototipos visuales para vender:**
→ **Bolt** o **Lovable**. Demo vivo durante la reunión con el cliente.

**Quieres solo componentes limpios:**
→ **v0**. Mejor código React/Tailwind listo para Next.js.

**Quieres un interno / CRUD empresarial:**
→ **Base44** o **Mocha**. DB, auth, deploy incluidos.

### 4.3 Claude Code en 2026: el CLI que se comió el mundo

Novedades clave:
- ✅ **Opus 4.7** como default (abril 2026).
- ✅ **Rediseño del Desktop app** (14 abr 2026): múltiples sesiones en paralelo, editor, diff viewer, preview HTML/PDF.
- ✅ **Routines**: automations que corren en la nube de Anthropic (no necesitas tu máquina encendida).
- ✅ **Skills**: carpetas de instrucciones + scripts que Claude carga dinámicamente.
- ✅ **MCP nativo**: 90+ plugins (Atlassian Rovo, GitLab, Render, Superpowers, Neon).
- ✅ **Auto mode** (marzo 2026) y **Advisor tool** (modelo advisor + executor).

**Éxito reportado (en casos reales):**
- Mythos Preview (abril 2026) encontró de forma autónoma una **vulnerabilidad RCE de 17 años en FreeBSD** (CVE-2026-4747) usando Claude Code + Opus 4.7.
- Empresas reportan **75% de éxito en codebases >50k LOC** con Claude Code.

### 4.4 El patrón "super-app strategy" (Ben Cord, abril 2026)

Después de probar Claude Code, Codex, Cursor y Manus, Ben Cord recomienda solo dos:
1. **Cursor** como IDE principal (velocidad de edición).
2. **Claude Code** como second brain (planning, refactor profundo, tareas largas).

Con un setup de 6 pasos:
1. Configurar `.cursor/rules` con las reglas del proyecto.
2. Instalar Claude Code con los MCPs relevantes (GitHub, Supabase, tu DB).
3. Crear `AGENTS.md` con el contrato del agente (del estándar Linux Foundation).
4. Usar Cursor para edición en línea; Claude Code CLI para tareas de >30 min.
5. Activar Claude Code Routines para validación continua (CI/CD).
6. Monitorear métricas: tokens consumidos, PRs aceptados, bugs introducidos.

### 4.5 Context Engineering: el nuevo prompt engineering

Más importante que el prompt es **qué información tiene disponible el modelo al ejecutar**.

**Las 6 técnicas clave:**
1. **Documentación .md al inicio del repo:** el modelo la lee automáticamente.
2. **Archivos de referencia (examples/).**
3. **Tests como especificación:** el modelo infiere intenciones desde los tests.
4. **CLAUDE.md / AGENTS.md:** contratos de convivencia humano-agente.
5. **MCP servers con contexto de negocio:** no solo API, sino semántica.
6. **Plantillas de prompt parametrizadas** (stories, ADRs, PRDs reusables).

### 4.6 Seguridad: el elefante en la sala

Según Veracode 2026, el **45% del código AI-generado tiene vulnerabilidades explotables**. Antes de producción:
- Code review humano obligatorio en repos serios.
- Análisis estático (Snyk, Sonar, CodeQL).
- Pruebas de prompt injection.
- No deployar vibe-coded en industrias reguladas sin auditoría externa.

## 📺 Videos ancla
- **Ben Cord** — *"How I'm Coding in 2026 (The Super-App Strategy)"* (abril 2026).
- **Ben Cord** — *"Vibe Coding With Cursor 3"* (abril 2026).
- **Tina Huang** — *"AI coding tools ranked from beginner to advanced"* (2026).

## 🧪 Lab 4 — "De idea a producción en 90 min"
**Duración:** 90 min · **Entregable:** app desplegada pública

Construye una app CRUD real (p. ej. gestor de tareas de equipo):
1. **Lovable** (30 min): prompt inicial, autenticación con Supabase, UI limpia.
2. **Export a GitHub**.
3. **Cursor** (30 min): añadir una feature compleja (dashboard con gráficas).
4. **Claude Code** (20 min): refactor y tests.
5. **Deploy** a Vercel (10 min).

## ✅ Evaluación
- Link a la app viva.
- Evidencia de los 3 tools usados (screenshots).
- Reflexión: ¿en qué tool se sintió mejor cada etapa?

---

# 🟨 MÓDULO 5 — Data Science y análisis avanzado con IA

**⏱️ Duración:** 1.5 horas · **Nivel:** Intermedio · **Modalidad:** Notebooks + IA

> **Tutor principal:** Tina Huang 🎥
> *"Always minimize effort and maximize outcome."*

## 🎯 Objetivos
- Usar IA como copiloto de todo el ciclo de data science.
- Construir pipelines RAG con n8n o LangGraph para consultas a datos internos.
- Entender qué habilidades de data science siguen siendo irreemplazables en 2026.

## 📚 Contenido

### 5.1 Las 4 fases del ciclo DS con copiloto IA

| Fase | Tarea | Copiloto recomendado | Tiempo típico ahorrado |
|---|---|---|---|
| **Explorar** | EDA, limpieza, descubrir patrones | ChatGPT Advanced Data Analysis / Claude + code execution | 60-80% |
| **Modelar** | Feature engineering, baseline, tuning | Cursor/Claude Code en Jupyter | 40-60% |
| **Evaluar** | Métricas, error analysis, slicing | Claude con contexto largo | 50-70% |
| **Comunicar** | Dashboards, decks, narrativa | NotebookLM + Canvas | 70-85% |

### 5.2 SQL con IA: del "escribe la query" al "analiza la base"

Patrón viejo (2023): "Claude, escríbeme un JOIN".

Patrón nuevo (2026): Le das al modelo acceso a la DB vía MCP (Snowflake, Postgres, BigQuery) + un diccionario de datos. El modelo:
- Explora la DB con queries.
- Propone hipótesis.
- Valida con sub-queries.
- Entrega un informe con números, gráficos y reservas metodológicas.

**Ejemplo real:** "¿Por qué cayó la conversión el mes pasado?" → el agente hace 15 queries, cruza 4 tablas, encuentra una caída por segmento mobile-iOS en una región, y recomienda action items.

### 5.3 RAG (Retrieval-Augmented Generation) sin sufrir

**Arquitectura mínima que funciona:**
1. **Ingesta:** documentos → embeddings → vector store (Supabase/Pinecone/Weaviate).
2. **Retrieval:** la consulta del usuario busca los K fragmentos más relevantes.
3. **Generation:** el LLM responde usando esos fragmentos como contexto.

**El nuevo estándar multimodal:**
Google lanzó su **primer embedding multimodal** (basado en Gemini): mapea texto, imágenes, video, audio y PDF al mismo espacio vectorial. Resultado: un solo pipeline para "busca en todos los archivos de la empresa", incluidos meetings grabados.

**Stack recomendado 2026:**
- Ingesta: n8n / LangChain.
- Embeddings: Gemini Embeddings o `text-embedding-3-large`.
- Vector DB: Supabase (si ya lo usas) / Pinecone (si serio).
- Generation: Claude Sonnet 4.6 (balance precio-calidad) o GPT-5.4 mini.
- Frontend: Lovable o Streamlit.

### 5.4 GPT-Rosalind y los modelos especializados

En abril 2026 OpenAI lanzó **GPT-Rosalind**, modelo para ciencias de la vida (farma, biotech, drug discovery). Es la señal de una tendencia:

> **Los modelos verticales están llegando.** Esperamos en los próximos meses modelos especializados en finanzas, legal, y seguramente healthcare clínico.

Implicación para DS: para casos altamente técnicos (química, bio, legal), vale la pena evaluar modelos de nicho antes de decidirse por uno frontera genérico.

### 5.5 Qué NO puede hacer la IA todavía (y por qué tu rol sigue valiendo)

- Juzgar la **validez causal** de un análisis (correlación vs. causa sigue siendo humano).
- Elegir **las métricas correctas** para un negocio concreto.
- Detectar **sesgos sistemáticos** en los datos de entrada.
- Comunicar **trade-offs** a un stakeholder no técnico.
- Diseñar **experimentos A/B** robustos.

**Tina Huang framework:** "minimize effort, maximize outcome". Tu trabajo ya NO es ejecutar queries — es hacer las preguntas correctas y curar las respuestas.

## 📺 Videos ancla
- **Tina Huang** — *"101 Ways to Use AI in Your Daily Life"*.
- **Tina Huang** — *"AI Skills Every Data Scientist Needs in 2026"*.
- **Jeff Su** — *"How to use NotebookLM for research that matters"*.

## 🧪 Lab 5 — "Chatbot de datos internos"
**Duración:** 60 min · **Entregable:** link funcional

Construye un RAG chatbot sobre un dataset público (ej. informes anuales SEC de 3 empresas). Stack:
1. Supabase con `pgvector`.
2. Embeddings con Gemini o OpenAI.
3. Agent en n8n que responde con citas.
4. Frontend en Lovable.

## ✅ Evaluación
- Pregunta compleja: "Compara la evolución del margen bruto de Apple, Microsoft y Google entre 2021 y 2024, explicando las 2 causas principales de divergencia."
- Tu bot debe responder con números exactos y citas a páginas.

---

# 🟧 MÓDULO 6 — Estrategia empresarial e implementación de IA

**⏱️ Duración:** 1.5 horas · **Nivel:** Liderazgo · **Modalidad:** Estudios de caso + frameworks

> **Tutor principal:** Marina Mogilko (Silicon Valley Girl) 🎥
> *"We're only 5% into the AI revolution."* — Reid Hoffman

## 🎯 Objetivos
- Construir un roadmap de adopción de IA de 12 meses para una empresa.
- Medir ROI de iniciativas de IA con métricas realistas.
- Gestionar el cambio cultural y el upskilling del equipo.
- Entender gobernanza, riesgos y regulación (EU AI Act + tendencias USA).

## 📚 Contenido

### 6.1 El estado de adopción empresarial (cifras clave 2026)

- **61% de organizaciones** declaran a OpenAI GPT como plataforma GenAI principal (Futurum Group, 1H 2026).
- **67% de organizaciones** corre IA en producción (no solo piloto).
- Mercado AI Platforms proyectado en **$292B para 2030** (Futurum).
- **78M nuevos empleos** por IA al 2030, pero **23% de roles** sufrirán disrupción mayor (WEF Future of Jobs Report, Davos 2026).
- Oracle anunció recorte de **20.000-30.000 empleos** para redirigir $8-10B a infra de IA. Es señal de reestructura masiva.

### 6.2 El framework "Buy / Build / Wrap" para cada iniciativa

| Estrategia | Cuándo | Ejemplo |
|---|---|---|
| **Buy** | Caso comoditizado, no diferencial | Licenciar ChatGPT Enterprise / Gemini Enterprise |
| **Build** | Core del negocio, con data única | Modelo custom / agentes propios sobre datos propietarios |
| **Wrap** | Necesitas UX custom sobre modelo existente | Construir tu app sobre Claude/GPT API con tu flujo |

### 6.3 El framework de Conor Grennan (NYU Stern)

> *"La mayoría no está atrasada por falta de tools, está atrasada por comportamientos."*

Pasos para una empresa:
1. **Audit:** ¿qué tools pagas? ¿qué procesos son candidatos? Inventario honesto.
2. **Pilot squad:** 3-5 personas power-user en distintos departamentos.
3. **Playbooks por rol:** un one-pager con prompts + flujos por puesto (Marketing, Ventas, Finanzas, Legal, HR).
4. **Métricas compartidas:** horas/semana ahorradas, calidad, NPS.
5. **Upskilling continuo:** 30 min/semana en grupo compartiendo hallazgos.

### 6.4 Los 5 riesgos que hay que gobernar

1. **Alucinaciones en decisiones:** Mitigación → RAG + human-in-the-loop.
2. **Fugas de datos:** Mitigación → ChatGPT Enterprise / Claude for Work / Gemini Enterprise (zero data retention).
3. **Vendor lock-in:** El cierre de Sora en abril 2026 enseñó a las empresas el costo de depender de un solo vendor. Mitigación → abstraer tu stack por MCP.
4. **Bias y fairness:** Auditorías periódicas.
5. **Regulación:** EU AI Act ya es vinculante en 2026 para sistemas de alto riesgo; USA empieza a tener marcos estatales.

### 6.5 Ejercicio de ROI — la calculadora honesta

Fórmula base:
```
ROI anual = (Horas ahorradas/semana × Costo hora × 52 semanas × N personas) - (Costo licencias + Costo implementación)
```

**Ejemplo:** Equipo legal de 15 personas, IA ahorra 4 h/semana por persona, costo hora $75:
- Ahorro bruto: 15 × 4 × 75 × 52 = $234.000/año
- Licencias (Claude for Work): 15 × $25 × 12 = $4.500/año
- Implementación: $30.000 una sola vez
- **ROI año 1: +$199.500 (+~575%)**

**Ojo:** muchos pilotos sobrestiman ahorros por "hora ahorrada". Pídelos medidos, no estimados.

### 6.6 Los 3 roles "hot" para los próximos 5 años (Ryan Roslansky, CEO LinkedIn)

1. **Data Annotator** (el humano que entrena al modelo).
2. **Data Center roles** (demanda masiva por infraestructura).
3. **Forward Deployed Engineer** (el ingeniero que vive en el cliente adaptando IA al contexto).

**Las 5 skills que importan (framework "5 Cs"):**
Curiosity · Courage · Creativity · Compassion · Communication.

### 6.7 El roadmap de 12 meses plantilla

| Mes | Fase | Actividades |
|---|---|---|
| 1-2 | **Discovery** | Audit, entrevistas, priorizar 3-5 casos. KPI baseline. |
| 3-4 | **Pilot** | Construir 1-2 pilotos alto-ROI con pilot squad. |
| 5-6 | **Expand** | Extender a otros departamentos. Lanzar playbooks por rol. |
| 7-8 | **Harden** | Gobernanza, seguridad, SOC2/ISO, training masivo. |
| 9-10 | **Scale** | Agentes en producción, integración stack empresa. |
| 11-12 | **Innovate** | Ventajas competitivas diferenciadas. Revisión 360°. |

## 📺 Videos ancla
- **Silicon Valley Girl** — episodio con *Reid Hoffman* (AI revolution al 5%).
- **Silicon Valley Girl** — episodio con *Ryan Roslansky* (LinkedIn, futuro del trabajo).
- **Silicon Valley Girl** — episodio con *Mustafa Suleyman* (Microsoft AI, agentes).
- **Silicon Valley Girl** — episodio con *Yossi Matias* (Google VP sobre AI skills gap).

## 🧪 Lab 6 — "Tu caso de negocio de IA"
**Duración:** 60 min · **Entregable:** deck de 10 slides

Prepara un plan de IA para TU empresa (o una que elijas):
1. Contexto y problema de negocio (1 slide).
2. 3 iniciativas priorizadas (3 slides).
3. Matriz Buy/Build/Wrap para cada una (1 slide).
4. ROI año 1 calculado (1 slide).
5. Roadmap 12 meses (1 slide).
6. Riesgos y gobernanza (1 slide).
7. Go/No-go criteria (1 slide).
8. Presupuesto y equipo (1 slide).

## ✅ Evaluación
- Presentación de 7 minutos al grupo, con Q&A de 3 min.
- Rubrica: viabilidad técnica (25%), ROI realista (25%), gestión del cambio (25%), riesgos (25%).

---

# 🏆 MÓDULO 7 — Capstone y roadmap personal

**⏱️ Duración:** 1 hora · **Nivel:** Integrador

## 🎯 Objetivos
- Integrar los 6 módulos en un proyecto propio.
- Definir tu sistema personal de aprendizaje continuo (Learning Loop adaptado).
- Crear tu "radar de IA" para los próximos 6 meses.

## 🧪 Capstone final

Elige UN track:

### Track A — Productividad en tu rol (baja barrera técnica)
Diseña y documenta el sistema AI-native completo para tu puesto:
- 5 workflows en Claude Cowork / NotebookLM / Gemini.
- Tu "AI swipe file" con ≥20 prompts.
- Métrica: horas/semana ahorradas.
- Video loom de 5 minutos explicando.

### Track B — Agente en producción (técnico)
Despliega UN agente real con usuarios reales:
- Trigger real (email/form/webhook).
- ≥2 tools MCP.
- Memoria persistente.
- Logging y métricas.
- Documentación pública.

### Track C — Producto vibe-coded (builder)
Construye y lanza UNA aplicación:
- Desde idea (Lovable) a producción (Cursor/Claude Code).
- Usuario real que la use ≥1 semana.
- Feedback recolectado.
- Plan de iteración.

### Track D — Plan de IA empresarial (liderazgo)
Construye y presenta el plan 12 meses de Módulo 6 a tu organización (o simulación).
Compromiso: ejecutar al menos Mes 1-2 en los 30 días siguientes.

## 🔁 El sistema que te llevas

**Rutina diaria (5 min):**
- Lee UNA newsletter. Sugerencias: *One Useful Thing*, *Silicon Valley Girl Newsletter*, *The Neuron*, *Workspace Essentials (Jeff Su)*.

**Rutina semanal (30 min):**
- Prueba UNA cosa nueva (Learning Loop).
- Actualiza tu AI swipe file.

**Rutina mensual (2 horas):**
- Revisa release notes de: Anthropic, OpenAI, Google AI, Cursor, Lovable, n8n.
- Replantea tus workflows con novedades.

**Rutina trimestral (medio día):**
- Re-evalúa tu stack: ¿sigue siendo el mejor?
- Actualiza tu "AI radar" (la hoja del Lab 0).

## 📅 Calendario de eventos clave 2026 a mirar
- **Anthropic DevConnect** (por confirmar, 2026).
- **Google I/O** (mayo 2026).
- **OpenAI DevDay** (otoño 2026).
- **WEF Davos 2027** (enero).

## 🎓 Diploma del curso
Al completar todos los módulos y el Capstone:
- Badge digital "AI-Native Professional 2026".
- Carta de certificación.
- Acceso a alumni-community para cohortes futuras.

---

# 📎 Anexos

## A. Stack recomendado para empresas (resumen)

**Productividad general:**
- Claude for Work (Cowork + Chat) — recomendado.
- Gemini Enterprise — si ya estás en Google Workspace.
- ChatGPT Enterprise — muy utilizado, pero ojo con vendor lock-in.
- NotebookLM — cerebro externo para equipos.

**Automatización:**
- n8n (self-hosted o cloud).
- Zapier AI para flujos simples sin ingeniería.

**Vibe coding:**
- Cursor + Claude Code (profesionales).
- Lovable + Supabase (MVPs y prototipos).

**Datos:**
- Snowflake + MCP de Cortex / Databricks.
- Supabase `pgvector` para RAG pequeños/medianos.

**Gobernanza:**
- SOC2 / ISO 27001 en los vendors.
- Cumplimiento EU AI Act.

## B. Librería de prompts plantillas
1. **Brief creativo** — "Actúa como director creativo senior…"
2. **Análisis FODA** — "Genera FODA de [empresa] con 3 fuentes citadas…"
3. **Resumen ejecutivo** — "Transforma este informe de 50 páginas en 1 página para CEO…"
4. **Email difícil** — "Reescribe este email siendo directo pero empático…"
5. **Código pull request review** — "Revisa este diff y destaca riesgos de seguridad…"
6. **Extracción de datos** — "Extrae de este PDF una tabla con columnas X, Y, Z…"
7. **Competitive research** — "Busca en web y produce una matriz comparativa…"
8. **Meeting prep** — "Dado este contexto, genera agenda y 5 preguntas clave…"
9. **Customer insight** — "Analiza estas 30 reseñas y agrupa en 5 temas…"
10. **Documentación** — "Convierte este código en documentación markdown…"

## C. Bibliografía y fuentes

**Lecturas fundamentales:**
- *One Useful Thing* — Ethan Mollick (newsletter).
- *The Vibe Coding Explosion: 138 Tools* — Till Freitag (marzo 2026).
- Reports: *WEF Future of Jobs 2026*, *Stanford AI Index 2026*, *Futurum AI Platforms Market Forecast*.

**Release notes oficiales a monitorear:**
- Anthropic: https://www.anthropic.com/news + release notes platform.claude.com
- OpenAI: https://openai.com/news
- Google Gemini: https://gemini.google/release-notes
- NotebookLM: blog oficial

**Comunidades:**
- AI Automation Society (Nate Herk) — 275K+ miembros.
- Lonely Octopus (Tina Huang).
- Latent Space (podcast).

## D. Glosario completo

*(Ver Módulo 1.4 y ampliar con definiciones formales)*

---

# 📌 Notas para quien imparte el curso

## Guión de facilitación
- Cada módulo: 70% contenido / 30% demo en vivo.
- Al final de cada módulo, 15 min de "show and tell" de participantes.
- Crear canal Slack/Teams de cohorte para compartir prompts y hallazgos.
- Rotar la "brújula": cada semana un participante expone un video de uno de los 6 creadores.

## Modalidades de entrega
- **Cohorte síncrona:** 6 semanas, 2h/sesión, con lab en casa.
- **Corporate masterclass:** 2 jornadas intensivas de 5h.
- **Self-paced + mentoría:** 90 días, videos grabados + 4 sesiones 1:1.

## Métricas de éxito del curso
- NPS >60.
- 80% completa los labs.
- Cada participante presenta al menos UN workflow adoptado en su trabajo.
- 6 meses después: encuesta de impacto en productividad.

---

*Curso diseñado con base en la investigación de novedades de IA entre octubre 2025 y abril 2026.*
*Actualizado al 18 de abril de 2026. Sujeto a revisión trimestral por la velocidad del sector.*

🚀 **¡Manos a la obra!**
