# Propuesta: Head of AI
### Construyendo la capacidad de IA como palanca de eficiencia y productividad

---

## 1. Contexto y oportunidad

### 1.1 Diagnóstico del estado actual
La empresa opera en un negocio marketplace de ridehailing en múltiples países, con más de 100 empleados y datos centralizados en una base de datos transaccional. Sin embargo, el patrón de explotación actual es:

**SQL → export → Google Sheets → dashboard/análisis/forecast → decisión humana.**

Esto tiene tres consecuencias de fondo:

- **La inteligencia vive en cabezas y hojas de cálculo**, no en sistemas. Cada decisión requiere un humano en el loop incluso cuando no aporta valor marginal.
- **El tiempo de ciclo entre dato y acción es alto** (horas o días), mientras que en un marketplace de movilidad el ciclo ideal es de segundos a minutos.
- **No hay escalabilidad ni defensibilidad**: el conocimiento no se acumula como activo; se consume en cada análisis.

Paralelamente existen activos que hoy están infrautilizados: un equipo de BI ya operativo, un equipo de ingeniería, datos de calidad en una sola fuente y un C-level patrocinador. IT se limita a proveer equipos, lo que da libertad de stack pero exige asumir responsabilidad sobre arquitectura y gobierno.

### 1.2 Por qué ahora
- El costo marginal de desplegar modelos (open source como Llama, frameworks maduros) ha caído drásticamente.
- Los competidores directos en ridehailing (globales y regionales) ya usan IA en matching, pricing, fraude y soporte. No adoptar no es una opción neutral; es una pérdida relativa.
- La empresa tiene la escala suficiente para que **pequeñas mejoras porcentuales generen impacto absoluto relevante** (1% más de matching eficiente en un marketplace de miles de viajes diarios = impacto directo en P&L).
- La sensibilidad con datos personales, lejos de ser un freno, es una ventaja si se diseña correctamente: modelos open-source desplegados internamente (Llama) permiten no enviar PII a terceros.

### 1.3 Tesis
> La empresa no necesita "hacer IA"; necesita **convertir decisiones repetitivas hoy humanas en sistemas**, y apalancar IA generativa para multiplicar la productividad de los equipos. El rol de Head of AI existe para orquestar esa transición sin fricción con BI, Ingeniería y Producto, y con privacidad como principio de diseño.

---

## 2. Visión y principios rectores

### 2.1 North Star
**Cada decisión repetitiva en la empresa debe tener un sistema detrás, y cada empleado debe tener un copiloto de IA que multiplique su productividad 2-5x en tareas cognitivas.**

### 2.2 Principios
1. **Privacy by design**: ningún dato personal sale de la infraestructura controlada. Modelos open-source self-hosted como default para cargas sensibles.
2. **Valor antes que sofisticación**: un modelo simple en producción supera a uno complejo en slides.
3. **BI y AI son un continuo, no silos**: el equipo de BI no es cliente, es socio. Parte del plan es elevar sus capacidades.
4. **Humanos en el loop donde importa**: automatizar decisiones repetitivas de bajo riesgo; mantener humanos en decisiones de alto impacto con asistencia IA.
5. **Medición rigurosa**: todo caso de uso tiene baseline, hipótesis de impacto y experimentación controlada (A/B o cohortes).
6. **Construir vs comprar con criterio**: comprar commodities (infra, observabilidad, vector DBs gestionadas); construir lo que es diferencial (matching, pricing, modelos fine-tuned con nuestros datos).
7. **Iteración corta y visible**: releases mensuales con impacto comunicable, no proyectos anuales.

---

## 3. Pilares estratégicos

Propongo nueve pilares. Los primeros cinco se alinean con los buckets que ya identificaste; los tres siguientes son habilitadores transversales que suelen olvidarse y son los que determinan el éxito o fracaso de la función. El noveno pilar — **Atlas** — es la plataforma interna que materializa todo lo anterior en una sola experiencia para el empleado y se convierte en la carta diferenciadora de la propuesta.

### Pilar 1: Datos y plataforma (foundation)
Es el cimiento. Sin esto, los demás pilares se construyen sobre arena.

### Pilar 2: Operaciones (marketplace intelligence)
El corazón del negocio: matching, pricing, supply, fraude, forecasting.

### Pilar 3: Producto y experiencia (IA embebida en UI/UX)
Cómo la IA aparece en la app para pasajeros y conductores.

### Pilar 4: Comunicaciones y soporte (conversational AI)
Interacciones automáticas y asistidas con usuarios y conductores.

### Pilar 5: Analítica y decisión (from insights to systems)
Pasar de dashboards a sistemas de decisión, incluyendo copilotos internos.

### Pilar 6: Seguridad y confianza (safety & trust)
Detección de incidentes, verificación, moderación. Crítico reputacional y regulatorio.

### Pilar 7: Gobierno, privacidad y ética (AI governance)
Políticas, controles, auditabilidad. Sin esto no hay licencia para operar.

### Pilar 8: Talento y cultura (AI literacy)
Cómo toda la empresa sube su nivel de IA, no solo el equipo central.

### Pilar 9: Atlas — Plataforma Interna de IA
El sistema operativo interno de la empresa. Un ecosistema único donde cada equipo tiene sus propios módulos de IA construidos sobre su conocimiento específico, corriendo sobre una infraestructura compartida de gobierno, seguridad y datos. Es el pilar que convierte a la empresa en **una organización que aprende** y el activo más difícil de replicar por competidores.

---

## 4. Casos de uso por pilar

Esta es la sección que deberías tener pre-cargada para responder cualquier pregunta del C-level sobre "¿qué harías concretamente?".

### 4.1 Datos y plataforma
- **Feature store**: repositorio central de features reutilizables (precio histórico por zona, comportamiento de usuario, densidad de conductores por hora). Evita que cada modelo reinvente las mismas variables.
- **Capa semántica**: diccionario único de métricas (qué es "viaje completado", "conductor activo", "usuario churneado") para que BI, AI y Producto hablen el mismo idioma.
- **Pipeline de streaming**: eventos en tiempo real (Kafka / Kinesis / Redpanda) para alimentar modelos que requieren baja latencia.
- **Data contracts**: acuerdos formales entre productores y consumidores de datos, para que un cambio upstream no rompa 10 modelos downstream.
- **Observabilidad de datos y modelos**: detección de drift, data quality, model performance en producción.
- **Sandbox de experimentación**: entorno seguro con datos anonimizados para prototipar rápido.

### 4.2 Operaciones (marketplace)
Aquí está el mayor ROI potencial. Ordenado por impacto típico:

- **ETA prediction mejorada**: un ETA más preciso sube conversión de reserva, reduce cancelaciones y mejora percepción de marca. Modelos de gradient boosting o redes neuronales sobre datos de tráfico, histórico de rutas y conductor.
- **Matching óptimo pasajero-conductor**: no siempre el conductor más cercano es el mejor match. Se puede optimizar por combinación de tiempo, rating, probabilidad de aceptación, balance del marketplace.
- **Pricing dinámico / surge inteligente**: modelos que balancean oferta y demanda sin castigar la experiencia. Reinforcement learning o modelos causales para medir elasticidad por zona y horario.
- **Supply positioning**: predecir dónde habrá demanda en los próximos 15-60 minutos y generar heatmaps de incentivos para conductores.
- **Detección de fraude**: cuentas múltiples, viajes fantasma, collusion entre conductor y pasajero, chargebacks, uso de GPS falso. Modelos de anomalía + grafos.
- **Churn prediction** (doble): pasajeros que están a punto de dejar de usar la app, y conductores que bajan horas conectadas. Permite intervenciones personalizadas.
- **Optimización de incentivos**: no todos los conductores responden igual a un bono. Uplift modeling para dar el incentivo correcto a la persona correcta.
- **LTV prediction**: valor esperado de pasajero/conductor para informar gasto en CAC.
- **Detección de rutas anómalas**: seguridad + fraude. Si un viaje se desvía mucho del óptimo o se detiene en zonas de riesgo, alertar.
- **Cancelación predecible**: modelo que, antes de asignar viaje, estima probabilidad de cancelación y ajusta asignación.

#### 4.2.1 Forecasting con ML — el salto desde Sheets a sistemas probabilísticos

Hoy los forecasts se hacen en Sheets con fórmulas, promedios móviles o regresiones simples. Funciona, pero tiene cuatro techos claros: **baja precisión**, **sin intervalos de confianza**, **no escala a múltiples dimensiones** y **no aprende de sus propios errores**. Un sistema de forecasting con ML supera esos cuatro techos simultáneamente.

**Qué predecir (cartera de forecasts)**
- Demanda de viajes por ciudad / zona / hora / día / semana.
- Oferta de conductores activos por zona y horario.
- Gap entre oferta y demanda (el más accionable).
- Tiempo promedio de espera (ETA agregado del marketplace).
- Tasa de cancelación por segmento.
- Revenue por ciudad, país y línea de negocio.
- Costos variables (incentivos, promociones, soporte).
- Activaciones y bajas de conductores.
- Tickets de soporte esperados (capacity planning).
- Efecto esperado de eventos (clima, partidos, conciertos, feriados).

**Por qué ML supera a Sheets**
- **Captura no linealidades**: un partido de fútbol, un viernes, y lluvia interactúan de forma compleja. Modelos ML las capturan; Sheets no.
- **Múltiples series simultáneas**: con modelos globales se pueden predecir cientos de zonas a la vez aprendiendo patrones comunes.
- **Features ricos**: clima, eventos, feriados locales, precio, competencia, días desde último incentivo — todo entra al modelo.
- **Forecasts probabilísticos**: no solo "esperamos 10,000 viajes", sino "hay 80% de probabilidad de estar entre 9,200 y 10,800". Esto cambia cómo se planifica.
- **Reentrenamiento automático**: el modelo mejora con cada semana de datos nuevos.

**Técnicas recomendadas por horizonte y caso**
- **Corto plazo / alta granularidad** (próximos 15-60 min, por zona): gradient boosting (LightGBM, XGBoost) con features de tiempo y contexto. Rápido, preciso, interpretable.
- **Mediano plazo / operativo** (1-14 días): modelos globales tipo DeepAR, N-BEATS o Temporal Fusion Transformers que predicen múltiples series con un solo modelo.
- **Largo plazo / planificación** (1-12 meses): Prophet o modelos jerárquicos con descomposición (tendencia, estacionalidad, eventos).
- **Probabilístico (con intervalos)**: quantile regression o modelos bayesianos cuando la incertidumbre importa más que el punto estimado (planificación de incentivos, presupuesto).
- **Forecasting jerárquico**: predicciones coherentes entre niveles (país = suma de ciudades = suma de zonas) con reconciliación automática.

**Features que mueven la aguja**
- Calendario: día de la semana, hora, feriado, víspera, semana del mes.
- Clima: temperatura, lluvia, viento (APIs externas integradas).
- Eventos: partidos, conciertos, protestas, cierres viales.
- Económicos: precio del combustible, inflación, tipo de cambio (por mercado).
- Internos: cambios de pricing, incentivos activos, campañas de marketing, cambios en la app.
- Competencia: señales indirectas cuando hay (precios públicos, tiempos de espera observables).
- Histórico reciente: lag features (1 día, 7 días, 28 días), medias móviles, ratios.

**Métricas de evaluación (cómo saber si es mejor que Sheets)**
- **MAPE / WAPE** para error porcentual.
- **RMSE** para error absoluto ponderado por magnitud.
- **Pinball loss / CRPS** para forecasts probabilísticos.
- **Skill score** vs baseline simple (ej. "igual que la semana pasada"). Este es el más honesto.
- **Impacto downstream**: ¿mejoró la asignación de incentivos? ¿redujo sobrestock de conductores? El forecast no es el fin; es input a decisiones.

**Arquitectura de producción**
- Pipeline de features que corre en batch o streaming según granularidad.
- Modelo versionado, trackeado en MLflow.
- Reentrenamiento automático semanal o mensual según caso.
- Detección de drift: si la distribución de inputs o errores cambia, alertar.
- Endpoint de inferencia consumido por Atlas (ver Pilar 9) y sistemas downstream.
- Backtesting continuo: el forecast de hace 30 días vs lo que realmente pasó, visible en un dashboard.

**Cómo se vende al C-level**
> *"Pasamos de forecasts estáticos con 20% de error a sistemas probabilísticos con 8-12% de error, reentrenados semanalmente, con intervalos de confianza que permiten planificar incentivos, staffing y marketing con mucha más precisión. Cada punto porcentual de mejora en forecast de demanda se traduce en menos conductores desperdiciados en zonas vacías y menos usuarios sin servicio en zonas calientes."*

### 4.3 Producto / UI/UX con IA
- **Búsqueda semántica de destinos**: "llévame a una cafetería tranquila cerca" en lugar de dirección exacta.
- **Recomendador de destinos**: predicción de a dónde quiere ir el usuario según hora, día, ubicación y patrones.
- **Onboarding inteligente de conductores**: verificación de documentos con OCR + liveness detection, reduciendo días de activación.
- **Asistente para conductores**: "¿dónde hay más demanda ahora?", "¿cuánto necesito trabajar hoy para cumplir mi meta?".
- **Resúmenes automáticos de viajes**: útil para empresas (viajes corporativos), taxes, control de gastos.
- **Ajuste dinámico de UI**: usuarios power ven opciones avanzadas; usuarios nuevos ven experiencia simplificada.
- **Accesibilidad**: voz-a-texto y texto-a-voz integrados para usuarios con discapacidades o manos ocupadas.

### 4.4 Comunicaciones y soporte
- **Agente conversacional de primer contacto**: atiende el 60-80% de consultas comunes (estado del viaje, reembolsos simples, actualización de datos) sin humano. Escalamiento inteligente a agente humano cuando corresponde.
- **Triage inteligente de tickets**: clasificación automática, ruteo al equipo correcto, detección de casos urgentes.
- **Resumen automático para agentes**: cuando un caso escala, el agente humano recibe un resumen del historial en 2 líneas en lugar de leer 30 mensajes.
- **Detección de sentimiento y churn en soporte**: identificar usuarios al borde de abandonar y ofrecer retención proactiva.
- **Mensajería proactiva personalizada**: promociones, alertas de demanda alta para conductores, recordatorios — todo con contenido y timing personalizados vía IA.
- **Traducción en tiempo real**: en mercados multilingües o entre pasajero y conductor que no hablan el mismo idioma.
- **Moderación de reseñas y comentarios**: detectar lenguaje ofensivo, quejas serias, discriminación.
- **Voice bots para IVR**: el 30-50% de llamadas a call center pueden resolverse con voz IA bien implementada.

### 4.5 Analítica y decisión (copilotos internos)
Esta es probablemente tu palanca más visible y rápida en los primeros 90 días.

- **"Chatea con tus datos"**: interfaz conversacional sobre el warehouse. Un gerente pregunta "¿cuánto creció ridehailing en Bogotá la semana pasada vs la anterior?" y obtiene respuesta con visualización. Reduce la cola de BI y empodera a la empresa.
- **Alertas inteligentes**: en lugar de dashboards que nadie mira, el sistema detecta anomalías (caída de conversión, spike de cancelaciones, drop en ciudad X) y notifica con contexto.
- **Narrativas automáticas**: reportes semanales/mensuales generados con LLM que explican el qué y el por qué, no solo el número.
- **Copilotos de análisis para BI**: asistente que escribe SQL, sugiere visualizaciones, encuentra segmentos anómalos. No reemplaza al analista, lo acelera 3-5x.
- **Simuladores de decisión**: "¿qué pasa si subo 5% los incentivos en Ciudad de México este fin de semana?" — modelo causal que estima el efecto esperado.
- **Forecast automatizado como servicio interno**: cualquier equipo puede pedir forecast de su métrica con self-service.
- **Asistente de documentación y conocimiento**: RAG sobre documentos internos (políticas, procesos, histórico de experimentos) para que cualquier empleado pregunte y reciba respuesta con fuentes.

#### 4.5.1 Agente Text-to-SQL — el desbloqueo del BI bottleneck

El dolor más concreto y resoluble de los primeros 90 días. Hoy cualquier pregunta de negocio que requiera un dato fresco pasa por: pedirle a BI → espera 1-5 días → entregable → pregunta de seguimiento → otra vuelta. El 70% de esas preguntas son repetitivas o sencillas. Un agente bien construido absorbe ese volumen y deja a BI para lo complejo.

**Qué hace el agente**
Recibe una pregunta en español natural como *"¿cuántos viajes completados tuvimos en Medellín el fin de semana pasado, separados por tipo de servicio?"* y entrega: una query SQL ejecutada sobre el warehouse, el resultado en tabla, una visualización sugerida, y una explicación en lenguaje claro del número. Si la pregunta es ambigua, repregunta. Si el resultado es sospechoso (un valor atípico, un join mal hecho), lo señala.

**Cómo funciona internamente**
- **Capa semántica como fuente de verdad**: el agente no consulta tablas raw; consulta modelos semánticos definidos (qué es "viaje completado", qué es "usuario activo"). Esto evita que dos respuestas al mismo concepto difieran.
- **Schema retrieval dinámico**: RAG sobre el diccionario de datos. El LLM solo ve las tablas/columnas relevantes para la pregunta, no el warehouse completo. Esto reduce costos y errores.
- **Few-shot con queries históricas**: se indexan queries validadas previamente (las que BI escribió y funcionaron). Ante una pregunta nueva, el agente encuentra las más parecidas y aprende del patrón.
- **Generación + validación**: el LLM genera la SQL; una capa de validación la parsea, verifica que use tablas permitidas, aplica límites de filas, revisa joins. Si falla, el agente reintenta con feedback.
- **Ejecución sandboxed**: conexión read-only, con quotas de costo y tiempo. Nunca puede escribir ni borrar.
- **Explicación de resultados**: segundo llamado al LLM para traducir el resultado a narrativa entendible.
- **Feedback loop**: el usuario puede marcar "respuesta correcta / incorrecta". Las correctas alimentan el índice de few-shot; las incorrectas generan alertas para revisión.

**Guardrails críticos (sin esto, no va a producción)**
- **Read-only** estricto a nivel de conexión de base de datos.
- **Allowlist de tablas y vistas** que el agente puede tocar.
- **Row-level security y masking**: si un usuario no debe ver PII de conductores, el agente tampoco se la enseña.
- **Límites de costo** por query y por usuario (evitar que un prompt genere un scan de toda la tabla de eventos).
- **Logging completo**: cada pregunta, query generada, resultado y usuario queda auditado.
- **Niveles de confianza**: el agente marca cuando no está seguro y sugiere "valida con BI antes de decidir con esto".
- **Métricas sensibles aprobadas**: ingresos, compensación, datos sensibles — solo con roles autorizados.

**Evolución por etapas**
- **Etapa 1** (MVP): responde preguntas sobre un subset de 10-20 métricas críticas bien modeladas. Acierto esperado: 85%+.
- **Etapa 2**: amplía a 50-100 métricas y soporta preguntas con filtros múltiples y comparaciones temporales.
- **Etapa 3**: preguntas analíticas compuestas ("qué segmentos muestran comportamiento atípico esta semana"), con ejecución de SQL + análisis estadístico básico.
- **Etapa 4** (agente full): puede encadenar queries, hacer follow-ups, generar reportes completos y enviarlos por Slack/email.

**Métricas de éxito**
- Volumen de preguntas respondidas sin intervención humana.
- Tasa de acierto validada por BI (sample semanal).
- Tiempo promedio de respuesta (vs. backlog de BI).
- Reducción de tickets repetitivos a BI.
- NPS interno del usuario del agente.
- Costo por pregunta resuelta.

**Dónde vive**
Como módulo dentro de **Atlas** (ver Pilar 9). Accesible desde Slack/Teams y desde la web interna. Mismo motor, diferente punto de entrada.

**Relación con BI**
Clave: no es reemplazo. BI define la capa semántica, valida ejemplos, revisa casos difíciles y sigue siendo dueño del conocimiento analítico. El agente **los libera** de lo repetitivo para que hagan lo estratégico. Vender esto internamente como *"BI 10x"*, no como *"BI reemplazado"*.

### 4.6 Seguridad y confianza
- **SOS inteligente**: detección de situaciones anómalas durante viajes (paradas no programadas, desvíos sospechosos, silencios largos en llamadas grabadas si aplica).
- **Verificación facial antes del viaje**: que el conductor que aparece en la app sea el que realmente está manejando.
- **Detección de comportamiento riesgoso**: frenadas bruscas, exceso de velocidad, uso del teléfono (con telemetría).
- **Scoring de riesgo por zona**: mapas de seguridad para mejor asignación de viajes nocturnos.
- **Detección de cuentas comprometidas**: login anómalo, cambio de dispositivo, patrones sospechosos.
- **Moderación automática de contenido** (fotos de perfil, mensajes en chat in-app).

### 4.7 Gobierno, privacidad y ética
No son casos de uso sino capacidades:

- **Política de uso de IA** clara y publicada internamente.
- **Comité de revisión de modelos de alto riesgo** (pricing, fraude, safety): antes de producción se revisa sesgos, fairness, impacto.
- **Data lineage**: saber de dónde viene cada dato y quién lo tocó.
- **PII detection & redaction**: sistemas automáticos que identifican y enmascaran datos personales antes de que entren a prompts o modelos.
- **Auditabilidad**: logs de qué modelo tomó qué decisión sobre qué usuario, con capacidad de revisión retroactiva.
- **Cumplimiento regional**: GDPR en Europa si aplica, LGPD Brasil, Ley 1581 Colombia, LFPDPPP México, etc.
- **Prompt injection defense**: especialmente en agentes conversacionales.
- **Red teaming interno**: equipo o proceso que intenta romper los modelos antes de que lo hagan usuarios maliciosos.
- **Explicabilidad**: en decisiones de alto impacto (bloquear cuenta, negar viaje) debe existir justificación comprensible.

### 4.8 Talento y cultura
- **AI Academy interna**: formación por niveles (literacy para todos, práctico para power users, técnico para BI/Eng).
- **Office hours semanales** del equipo de AI para cualquier empleado.
- **Hackathons internos** trimestrales con casos reales.
- **Librería de prompts y agentes internos** reutilizables.
- **Licencias corporativas** de copilotos (Claude, ChatGPT, Copilot) con gobierno de uso.
- **Métricas de adopción** de IA por equipo.

### 4.9 Atlas — Plataforma Interna de IA

**La idea en una frase**: un ecosistema único, interno, donde cada equipo tiene sus propios módulos de IA construidos sobre su conocimiento específico, corriendo sobre una infraestructura compartida de gobierno, seguridad y datos. No es un chatbot más ni una wiki con IA: es el **sistema operativo interno de la empresa** para la era de la IA.

#### 4.9.1 Problema que resuelve
Hoy, incluso sin IA, los equipos internos sufren problemas estructurales que se amplificarán si cada uno construye su solución de IA por separado:
- **Fragmentación**: cada equipo tiene sus docs, sheets, procesos y tickets. El conocimiento vive en silos.
- **Reinvención constante**: City Ops en Bogotá resuelve el mismo problema que City Ops en Lima sin enterarse.
- **Dependencia de personas clave**: cuando alguien renuncia, se lleva el 40% del conocimiento operativo.
- **Onboarding lento**: un nuevo city manager tarda meses en ser productivo.
- **Herramientas dispersas**: Notion, Slack, Sheets, JIRA, correos.
- **IA improvisada**: cada equipo monta asistentes con ChatGPT pegando datos sensibles, sin gobierno ni reuso.

Si no se resuelve con arquitectura, en 12 meses habrá 15 asistentes improvisados, ninguno conectado, todos con PII expuesta y ninguno con impacto medible.

#### 4.9.2 La visión del empleado
Cualquier empleado abre **una sola app interna** (Atlas) y encuentra:
- Su **copiloto personal**, que sabe de su rol, proyectos y documentos.
- Los **módulos de su equipo** (simulador de incentivos, asistente legal, analizador de tickets).
- Un **catálogo de módulos de otros equipos** accesibles con los permisos correctos.
- Una **base de conocimiento viva** que se actualiza con lo que el equipo produce.
- **Workflows automatizados** que ejecutan tareas, no solo responden.
- Todo auditado, con PII protegida, con trazabilidad completa.

El empleado no sabe ni necesita saber qué modelo corre detrás. Solo usa **sus herramientas**.

#### 4.9.3 Arquitectura de tres capas

**Capa 1 — Shell / plataforma base**: autenticación SSO, control de permisos por equipo/rol/módulo, UX unificada, gestión de sesiones e historial, panel de administración, observabilidad.

**Capa 2 — Servicios compartidos**: lo que no tiene que reinventarse en cada módulo.
- **LLM Gateway**: una sola puerta de salida hacia modelos (Llama self-hosted por default; Claude/GPT para casos aprobados). Rate limiting, logging, PII redaction, fallbacks.
- **Vector DB** compartido con namespaces por equipo.
- **Feature store** común con el pilar de plataforma de datos.
- **Motor de RAG estándar**: ingestión, chunking, embeddings, retrieval reutilizables.
- **Motor de agentes**: framework común para orquestar herramientas (llamar APIs, ejecutar queries, mandar emails).
- **Motor de workflows**: automatizaciones multi-step con aprobaciones humanas y triggers.
- **Auditoría y trazabilidad**: toda interacción queda registrada.
- **Evaluaciones**: tests automáticos de calidad por módulo.

**Capa 3 — Módulos por equipo**: cada módulo tiene su base de conocimiento, prompts, herramientas conectadas, equipo dueño y métricas.

#### 4.9.4 Tipos de módulos (patrones reutilizables)
1. **Copiloto conversacional** → Q&A sobre conocimiento del equipo.
2. **Agente de acción** → ejecuta tareas ("genera reporte semanal y mándalo").
3. **Workflow automatizado** → proceso multi-step con humano en el loop.
4. **Simulador / decisión asistida** → "¿qué pasa si subo el incentivo 5%?" con respuesta cuantitativa.
5. **Dashboard narrado** → visualización + explicación en lenguaje natural.
6. **Analizador de contenido** → procesa tickets, reseñas, grabaciones, contratos.
7. **Generador** → crea artefactos (emails, borradores, creativos).

#### 4.9.5 Ejemplos de módulos por equipo (ridehailing)

**Operaciones y City Managers**
- **City Copilot**: asistente que sabe todo de una ciudad (métricas, eventos, incidentes, decisiones, notas del team).
- **Simulador de incentivos**: proyecta impacto de cambios en bonos por zona.
- **Incident Response Assistant**: ante un incidente, guía al team por el runbook y ayuda a comunicar.
- **Competition Watch**: monitoreo automatizado de acciones de competidores por país.

**Soporte al cliente**
- **Agent Copilot**: asiste al agente humano con respuestas sugeridas, resumen de historial y política aplicable.
- **Quality Analyzer**: revisa conversaciones cerradas y detecta problemas de atención.
- **Knowledge Keeper**: base viva de políticas actualizada con cada cambio.

**Finanzas**
- **Reconciliation Agent**: procesa cierres mensuales, detecta discrepancias, genera explicaciones.
- **Invoice Analyzer**: procesa facturas, extrae datos, rutea aprobaciones.
- **Financial Q&A**: "¿cuánto gastamos en incentivos en Perú en Q2?" con respuesta inmediata.

**Legal y Compliance**
- **Contract Review Assistant**: primer filtro con resaltado de cláusulas sensibles.
- **Regulatory Monitor**: monitoreo de cambios regulatorios en movilidad por país.
- **Policy Q&A**: consulta de políticas internas para cualquier empleado.

**People / HR**
- **Onboarding Buddy**: guía personalizada para nuevos empleados.
- **Policy Assistant**: vacaciones, beneficios, procedimientos.
- **Performance Review Helper**: asiste a managers en escribir reviews con evidencia.

**Producto**
- **User Research Synthesizer**: procesa entrevistas y surveys, extrae temas recurrentes.
- **Experiment Analyzer**: explica resultados de A/B tests con recomendaciones.
- **Feature Request Router**: clasifica peticiones y las enruta al equipo correcto.

**BI / Data**
- **Data Copilot / Text-to-SQL** (ver 4.5.1): el módulo estrella del año 1.
- **Metric Explainer**: por qué cayó una métrica, con análisis automático de dimensiones.
- **Report Automator**: genera reportes recurrentes con narrativa.

**Marketing y CRM**
- **Creative Generator**: borradores de emails, push notifications, copy.
- **Segment Builder**: arma segmentos conversacionalmente.
- **Campaign Analyzer**: evalúa resultados post-campaña.

**Seguridad / Fraude**
- **Fraud Investigator Copilot**: asiste al analista en casos complejos.
- **Appeal Review Assistant**: apoya revisión humana de apelaciones de conductores.

**Ingeniería**
- **Runbook Copilot**: ante un incidente, guía al on-call.
- **PR Reviewer**: revisión inicial de pull requests.
- **Architecture Q&A**: asistente sobre sistemas y documentación técnica.

#### 4.9.6 La base de conocimiento — el activo oculto
La parte más poderosa de Atlas no es la IA; es lo que convierte a la empresa en **una organización que aprende**:
- Cada equipo tiene **su propia base** (docs, decisiones, runbooks, histórico).
- La base se **alimenta automáticamente** de las fuentes que ya usa (Drive, Notion, Slack channels seleccionados, repos, tickets).
- Los módulos consumen esa base vía RAG.
- Las interacciones útiles se **promueven a la base**, creando loop de aprendizaje.
- Control de acceso granular por equipo y sensibilidad.

**Consecuencia estratégica**: el conocimiento deja de ser propiedad de personas y se convierte en activo de la empresa. Cuando alguien renuncia, su conocimiento persiste.

#### 4.9.7 Roadmap de Atlas

**Fase 1 (0-90 días): prueba de concepto**
- Shell básico con autenticación y un solo módulo funcionando.
- Primer módulo recomendado: **Data Copilot / Text-to-SQL** (máxima visibilidad) o **Onboarding Buddy** (bajo costo, impacto emocional alto).
- Servicios compartidos mínimos: LLM gateway, vector DB, logging.

**Fase 2 (mes 4-9): 3-5 módulos en producción**
- 2-3 equipos early adopters con dolor claro y champion interno.
- Co-creación, no imposición.
- Estandarización de plantillas a partir de lo que funciona.
- Métricas de adopción y valor establecidas.

**Fase 3 (mes 9-18): self-service parcial**
- Plantillas de módulos parametrizables por equipos.
- SDK / low-code interno para que equipos técnicos construyan con supervisión.
- Catálogo con ranking de módulos más usados.
- Gobierno formal: aprobación, criterios de calidad, sunsetting.

**Fase 4 (mes 18+): plataforma viva**
- 15-30 módulos activos.
- Los equipos proponen y construyen con mínima intervención del equipo central.
- Plataforma posicionada como **ventaja competitiva no replicable** rápidamente por competidores.

#### 4.9.8 Gobierno de Atlas
- **Un equipo dueño de la plataforma** (shell + servicios compartidos): dentro del equipo de AI.
- **Un dueño por módulo** dentro del equipo que lo usa, no del equipo de AI.
- **Review de nuevos módulos** antes de promoción (seguridad, privacidad, valor esperado).
- **Métricas de salud por módulo**: adopción, satisfacción, costo, impacto. Los zombies se jubilan.
- **Política de datos clara**: qué puede indexarse, qué no, quién decide.
- **Versionado y changelog** por módulo.

#### 4.9.9 Beneficios estratégicos
1. **Productividad compuesta**: cada módulo ahorra horas; el efecto agregado escala con módulos × usuarios.
2. **Onboarding 2-3x más rápido** en roles operativos.
3. **Reducción de dependencia de personas clave**.
4. **Gobierno centralizado**: un solo lugar para políticas de privacidad y seguridad.
5. **Escala de aprendizaje**: lo que funciona en un mercado se despliega a otros en días.
6. **Diferenciación en reclutamiento**: talento técnico top se siente atraído.
7. **Activo de la empresa**: la plataforma y sus módulos son propiedad intelectual.
8. **Menos fuga de PII**: los empleados dejan de pegar datos sensibles en ChatGPT público porque tienen alternativa interna mejor.

#### 4.9.10 Riesgos específicos y mitigación

| Riesgo | Mitigación |
|---|---|
| La plataforma se construye y nadie la usa | Co-creación con equipos, champions internos, métricas de adopción desde día 1 |
| Sobre-ingeniería ("construir algo perfecto") | Shell simple primero; ganar con 1 módulo antes de generalizar |
| Cuello de botella (todo pasa por AI team) | Self-service progresivo; plantillas; empoderar equipos técnicos |
| Módulos de baja calidad erosionan confianza | Proceso de review + criterios de promoción + sunsetting |
| Conflicto con Notion, Confluence, Slack | No reemplazar; **agregar capa de IA sobre lo existente** |
| Permisos se vuelven caóticos | Modelo RBAC claro desde inicio; auditoría trimestral |
| Costo de cómputo escala inesperado | Observabilidad de uso; quotas por módulo; optimización por caso |

#### 4.9.11 Relación con la plataforma de configuraciones existente
La **plataforma de configuraciones actual** sirve al usuario final (pasajero, conductor) y define cómo interactúan con el producto. **Atlas** sirve al empleado y define cómo la empresa opera y aprende. Son **complementarias, no competidoras**. Pueden compartir infraestructura (auth, logging) y aprendizajes de UX, pero sus públicos y objetivos son distintos. Largo plazo podrían converger en una plataforma corporativa unificada con dos dominios (externo e interno), pero no es requisito.

#### 4.9.12 Mensaje de venta al C-level
> *"Hoy cada equipo pelea solo con sus datos, procesos y conocimiento. Propongo construir el **sistema nervioso interno de la empresa**: una plataforma donde cada equipo tiene sus módulos de IA, con su conocimiento, seguros, auditables y conectados. Empezamos con un módulo en 90 días. En 18 meses tendremos una capacidad que ningún competidor de ridehailing en la región tiene."*

---

## 5. Modelo operativo

### 5.1 Estructura propuesta del equipo
Empezar pequeño y crecer con evidencia de impacto. Fase inicial sugerida (primeros 6-9 meses):

- **Head of AI** (tú): estrategia, stakeholders, priorización, gobierno.
- **1-2 ML Engineers**: producción de modelos (matching, pricing, fraude).
- **1 Data/Analytics Engineer**: feature store, pipelines, colaboración cercana con BI existente.
- **1 Applied AI Engineer / GenAI Engineer**: copilotos internos, agentes conversacionales, RAG.
- **1 Product Manager de AI** (part-time o compartido al inicio): dueño del backlog de casos de uso, métricas de éxito.

Fase de escalamiento (mes 9-18): sumar MLOps, un especialista en responsible AI, y roles duplicados en áreas de mayor demanda.

### 5.2 Relación con otros equipos
- **BI**: socios, no clientes. Mitad del roadmap se ejecuta con ellos. Ellos aportan conocimiento profundo del dato; AI aporta modelado avanzado y deploy productivo. Eventualmente podrían reportar en una misma estructura (Data & AI), pero al inicio mantener independencia con colaboración formalizada.
- **Ingeniería**: aliados para integración de modelos en producto. Se define un contrato de APIs y SLAs. AI no despliega directamente en producción del app; lo hace a través de endpoints consumidos por Eng.
- **Producto**: co-owners de casos de uso de cara al usuario. PM de Producto y PM de AI trabajan en dupla.
- **Operaciones / City managers**: clientes internos principales en la fase 1 (matching, pricing, incentivos).
- **Legal y Compliance**: revisión temprana de casos sensibles. Se les incluye desde la ideación, no al final.
- **IT**: proveedor de infra base. Se negocia acceso cloud, políticas de red, presupuesto de cómputo.

### 5.3 Formas de trabajo
- Dual-track: **descubrimiento** (investigación, prototipado) y **entrega** (modelos en producción) en paralelo.
- **OKRs trimestrales** con métricas de negocio, no métricas técnicas. Evitar "precisión del modelo" como OKR; usar "reducción de cancelaciones" o "incremento de matching rate".
- **Comité de priorización** mensual con C-level y heads de área para revisar roadmap.
- **Demos quincenales** abiertas a toda la empresa.
- **Post-mortems y learning reviews** después de cada experimento, exitoso o no.

---

## 6. Roadmap

### Fase 0 — Primeros 90 días: Escuchar, diagnosticar, ganar credibilidad
- Entrevistas con todos los C-level y heads (al menos 20-30 conversaciones).
- Inventario de datos, fuentes, modelos existentes, dashboards críticos.
- Mapeo de dolores repetitivos por área.
- Publicación del documento estratégico (este que estás preparando) validado con stakeholders.
- **2-3 quick wins** en paralelo (ver sección siguiente).
- Definición de políticas de privacidad y gobierno mínimo viable.
- Primer hire clave (probablemente un ML Engineer senior o GenAI Engineer).
- **Atlas v0.1**: shell básico + primer módulo (Data Copilot / Text-to-SQL) en producción interna.

### Fase 1 — Mes 4 a 9: Cimientos y primeros sistemas en producción
- Feature store operativo.
- Capa semántica unificada con BI.
- Primer modelo crítico en producción (candidato: ETA mejorada, fraude, o churn).
- **Forecasting ML** en producción para al menos una ciudad/país piloto, con comparación de precisión vs Sheets.
- **Atlas v1.0**: 3-5 módulos activos cubriendo al menos 2-3 equipos distintos (ej. Data, City Ops, Soporte).
- Agente de soporte nivel 1 en piloto en un mercado pequeño.
- Framework de experimentación A/B maduro.

### Fase 2 — Mes 9 a 18: Escalamiento y diferenciación
- Matching/pricing bajo modelos propios en todos los mercados relevantes.
- **Forecasting ML jerárquico** (país → ciudad → zona) con intervalos de confianza en producción.
- Agente conversacional de soporte cubriendo >50% de volumen.
- **Atlas v2.0**: 10+ módulos activos, plantillas parametrizables, primeros equipos construyendo sus propios módulos con supervisión.
- Programa de responsible AI formalizado y auditable.
- AI Academy interna en marcha.
- Expansión del equipo a 8-12 personas.

### Fase 3 — Mes 18 a 36: Ventaja competitiva sostenible
- Plataforma de IA como activo estratégico de la empresa, no proyecto.
- Modelos fine-tuned propios (Llama fine-tuneado con datos del dominio) difíciles de replicar.
- **Atlas como foso competitivo**: 15-30 módulos en uso, conocimiento acumulado de la empresa como activo, onboarding medido en días en lugar de meses.
- Exploración de productos nuevos habilitados por IA (ej. servicios B2B de movilidad con optimización predictiva).
- Contribuciones open-source o publicaciones que posicionen la marca como líder técnico regional.

---

## 7. Quick wins para los primeros 90 días

Elegir 2-3 que sean **visibles, medibles y relativamente baratos**:

1. **Atlas v0.1 con Data Copilot (Text-to-SQL)**: primera versión de la plataforma interna con un solo módulo — el agente que responde preguntas de datos en lenguaje natural. Reduce backlog de BI, entusiasma al C-level, y sienta las bases arquitectónicas para todo lo que viene. Es el quick win y la declaración de intenciones al mismo tiempo.
2. **Automatización de reportes recurrentes**: los reportes que hoy alguien arma manualmente cada lunes, generados automáticamente con narrativa IA. Impacto: horas-persona ahorradas, visible. Puede vivir como módulo de Atlas desde el día 1.
3. **Clasificador de tickets de soporte**: modelo simple que rutea tickets al equipo correcto. Impacto: reducción en tiempo de primera respuesta.
4. **Detector de cancelaciones anómalas por ciudad**: alerta en tiempo real cuando una zona supera su baseline. Impacto: city managers toman acción temprana.
5. **Prototipo de forecasting ML para una ciudad piloto**: reemplazar el forecast en Sheets de una ciudad por un modelo ML, comparar precisión y vender el caso para escalarlo. Impacto: evidencia concreta del salto de capacidad.
6. **Asistente de onboarding de conductores con OCR**: acelera activación. Impacto: conductores activos más rápido = oferta.

---

## 8. KPIs y medición

### 8.1 KPIs de negocio (cómo se mide el éxito real del área)
- **Tasa de matching exitoso** (+X%)
- **Reducción de cancelaciones** (-Y%)
- **Reducción de costo por ticket de soporte** (-Z%)
- **Tiempo medio de activación de conductor** (-W%)
- **Fraude detectado / pérdidas evitadas** (USD)
- **Horas-persona ahorradas con copilotos internos** (medido por encuestas + telemetría)
- **Revenue incremental atribuible** a iniciativas de pricing/matching

### 8.2 KPIs de capacidad (salud del área)
- Modelos en producción
- Uptime y latencia de modelos
- Tiempo promedio de ciclo idea → producción
- Adopción de copilotos internos (DAU/MAU)
- NPS interno del área de AI
- % de empleados que completaron AI literacy básica
- **Atlas: número de módulos activos, usuarios activos semanales, preguntas/acciones ejecutadas**
- **Text-to-SQL: tasa de acierto validada por BI, volumen respondido sin intervención humana, reducción de tickets repetitivos a BI**
- **Forecasting: mejora de MAPE vs. baseline Sheets por caso, cobertura de intervalos de confianza**

### 8.3 Principio
Todo caso de uso debe tener **baseline definido antes de empezar**, hipótesis de impacto y plan de medición. Nada se aprueba sin esto.

---

## 9. Gobierno, privacidad y riesgo

Dado que la empresa es sensible con política de datos, este pilar merece atención especial y debería ser uno de los diferenciadores de tu propuesta.

### 9.1 Pilares de gobierno
- **Clasificación de datos**: qué es público, interno, confidencial, restringido.
- **Matriz de riesgo de modelos**: cada modelo clasificado por riesgo (bajo/medio/alto/crítico), con requisitos de aprobación y monitoreo proporcionales.
- **Revisión previa a producción** para modelos de riesgo alto/crítico (fraude, pricing, safety).
- **Registro central de modelos**: qué modelos existen, quién los mantiene, qué datos usan, cuándo se reentrenan.
- **Auditoría trimestral** de modelos en producción.

### 9.2 Privacidad aplicada
- **Default**: inferencia con modelos self-hosted (Llama) para cualquier dato que contenga PII.
- **Uso de modelos externos (Claude, GPT, etc.)** solo con datos anonimizados, contratos de no-retención y casos de uso aprobados.
- **PII scanning** automático en todos los prompts enviados a APIs externas.
- **Derecho al olvido** implementado técnicamente en features y embeddings, no solo en la DB transaccional.
- **Differential privacy** donde aplique para analítica agregada.

### 9.3 Ética
- Revisión de fairness en modelos que afectan a conductores (ranking, asignación, bloqueos).
- Transparencia con conductores sobre cómo se toman decisiones que los afectan.
- Canal de apelación humana en decisiones automáticas de alto impacto.

---

## 10. Stack tecnológico propuesto

Recomendación de punto de partida, sujeto a validación con IT e Ingeniería:

- **Lenguaje principal**: Python (modelos, agentes) + SQL (features, analítica).
- **Warehouse / Lakehouse**: lo que ya exista (Snowflake, BigQuery, Redshift, Databricks). Si no hay, evaluar Databricks o BigQuery.
- **Feature store**: Feast (open source) o Tecton (managed).
- **Orquestación**: Airflow o Prefect.
- **MLOps**: MLflow + Weights & Biases; o plataforma integrada tipo Databricks.
- **Serving**: FastAPI + contenedores; para latencia baja, Triton o BentoML.
- **Streaming**: Kafka / Redpanda + Flink o Spark Streaming.
- **LLMs self-hosted**: Llama 3+ sobre GPUs gestionadas (on-prem, AWS, GCP o Azure según política).
- **LLMs externos**: Claude, GPT-4 para casos no sensibles y prototipado rápido.
- **Vector DB**: pgvector (simple), Qdrant o Weaviate (escala).
- **Observabilidad**: Evidently (drift), Arize o Fiddler (model monitoring).
- **Experimentación**: plataforma A/B interna o GrowthBook.
- **Seguridad**: gateway de LLMs (ej. LiteLLM + capa propia) para log, rate limit y PII redaction.

Principio: **pocos componentes, bien dominados**, en lugar de zoo tecnológico.

---

## 11. Presupuesto y recursos (marco)

Sin cifras exactas (depende de moneda, país, seniority), propongo pensarlo en **tres cubos**:

1. **Personas** (70-80% del gasto): 5-7 FTEs en los primeros 12 meses.
2. **Cómputo e infraestructura** (15-20%): GPUs para self-hosting, cloud compute, storage, herramientas.
3. **Software y APIs** (5-10%): licencias de copilotos, APIs de LLMs externos, herramientas MLOps.

Modelo de aprobación por fases: se presenta un budget anual con tramos desbloqueables por hitos (milestone-based funding), no todo al inicio. Esto reduce riesgo para el C-level y disciplina al equipo.

---

## 12. Riesgos y mitigación

| Riesgo | Mitigación |
|---|---|
| Sobre-promesa al C-level | Roadmap con entregas mensuales; no prometer ROI antes de baseline medido |
| Conflicto con BI/Eng | Modelo de colaboración formal desde día 1; BI como socios no clientes |
| Fuga de talento | Compensación competitiva, proyectos de alto impacto, cultura de aprendizaje |
| Modelo en producción que causa daño (pricing injusto, bloqueo erróneo) | Comité de revisión + monitoreo + canal de apelación |
| Filtración de datos personales vía LLMs externos | Gateway con PII redaction, default a modelos self-hosted |
| Dependencia de un solo cloud / proveedor | Diseño portable; evitar lock-in donde sea razonable |
| Hype interno y expectativas irreales | Comunicación honesta; diferenciar experimentos de productos |
| Deuda técnica temprana | Desde el inicio: tests, CI/CD, documentación, observabilidad |

---

## 13. Narrativa para el C-level

Cuando resumas este documento, la propuesta se puede vender en cuatro mensajes:

1. **"No estamos haciendo IA por moda. Estamos convirtiendo decisiones humanas repetitivas en sistemas, y dando copilotos a cada empleado para que rinda 3x."** — el mensaje de productividad y eficiencia.
2. **"Nuestro activo más sensible son los datos. La arquitectura que propongo pone privacidad en el centro: Llama self-hosted, gobierno formal, auditabilidad."** — el mensaje de confianza y riesgo controlado.
3. **"Construimos Atlas, el sistema nervioso interno de la empresa. Una sola plataforma donde cada equipo tiene sus módulos de IA con su conocimiento propio. Es el activo que ningún competidor puede replicar copiando nuestros modelos, porque su valor está en el conocimiento acumulado."** — el mensaje de diferenciación y foso competitivo.
4. **"En 90 días verán Atlas v0.1 con el Data Copilot funcionando, en 12 meses tendremos sistemas en producción afectando el P&L, en 24 meses seremos líderes técnicos en la región."** — el mensaje de tracción y ambición.

La estructura ideal del documento ejecutivo (que derivarás de este) es:

- 1 página: visión y tesis.
- 1 página: diagnóstico actual.
- 2 páginas: pilares y casos de uso priorizados.
- 1 página: roadmap y quick wins.
- 1 página: KPIs y medición.
- 1 página: equipo y presupuesto marco.
- 1 página: gobierno y privacidad.
- 1 página: riesgos y preguntas abiertas.

---

## 14. Preguntas abiertas para validar con el C-level

Incluir esta sección al final del documento muestra madurez y crea espacio de decisión conjunta:

- ¿El alcance del cargo incluye eventualmente BI, o se mantienen separados?
- ¿Qué apetito de riesgo hay para automatización de decisiones con impacto en usuarios (bloqueo, pricing)?
- ¿Cuál es el horizonte de inversión comprometido? ¿12, 24, 36 meses?
- ¿Hay restricciones sobre uso de cloud público vs on-prem?
- ¿Qué métricas de P&L podemos mover y en qué magnitud constituye éxito?
- ¿Qué mercados/países son prioritarios para pilotos?
- ¿El cargo tiene representación en comité ejecutivo?
- ¿Hay benchmarks internos contra competencia que debamos considerar?

---

## 15. Posicionamiento personal

Dado que también estás construyendo tu posicionamiento interno, algunas recomendaciones:

- **No presentes esto como "lo que voy a hacer", sino como "lo que la empresa necesita"**. Tú eres el vehículo, no el protagonista.
- **Involucra a stakeholders antes de presentar**: que el documento llegue al comité con aliados ya ganados.
- **Ten listos 3 casos de uso con números de impacto estimado** para preguntas específicas.
- **Anticipa objeciones**: "es caro", "BI ya lo hace", "no tenemos datos suficientes", "IT no lo permitirá". Ten respuestas preparadas.
- **Propón una "prueba visible"** en los primeros 30-45 días (ej. el copiloto de datos funcionando) para que nadie dude de la capacidad de ejecución.
- **Documenta tu visión pública**: un post interno mensual sobre aprendizajes y progreso te posiciona como referente.

---

*Documento de trabajo. Próximos pasos sugeridos: (1) validar supuestos con 2-3 C-level clave; (2) priorizar 3-5 casos de uso de la sección 4 como foco de año 1; (3) condensar en versión ejecutiva de 8-10 páginas.*
