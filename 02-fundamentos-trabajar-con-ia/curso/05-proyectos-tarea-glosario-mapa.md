# 🛠️ PROYECTOS — ELIGE TU CAMINO

Cinco proyectos guiados, uno por nivel de la escalera. **No tienes que hacerlos todos ni en orden:** elige el que corresponda a tu nivel actual y al tipo de proyecto que quieres desarrollar.

## P1 · Proyecto solo con chat (Nivel 1)
**"Análisis de un documento con verificación"**

1. Sube un documento (informe, contrato, datos) al chat
2. Usa la fórmula de 5 ingredientes (rol + contexto + tarea + formato + ejemplo):
   ```
   Eres un analista senior. Analiza este documento y entrégame:
   resumen de 5 líneas, los 3 puntos más importantes, y 2 riesgos
   que detectes. Si te falta información, pregúntame primero.
   ```
3. Itera: "Bien. Ahora hazlo más directo y agrega recomendaciones."
4. Verifica: "Dame la parte exacta del documento que respalda cada punto."

**Lo que practicas:** prompts, iteración, verificación anti-alucinaciones.

## P2 · Proyecto con herramientas conectadas (Nivel 2)
**"Mi semana, organizada por la IA"**

1. Conecta tus conectores (MCP) de correo y calendario en Claude
2. Pide:
   ```
   Revisa mis correos sin responder de esta semana y mi calendario.
   Hazme una lista de: respuestas pendientes por prioridad,
   reuniones que necesitan preparación, y conflictos de agenda.
   ```
3. Crea tu primera Skill personal: instrucciones de cómo te gusta ese resumen (formato, orden, tono) para no repetirlas cada semana

**Lo que practicas:** MCP/conectores, tu primera Skill.

## P3 · Proyecto delegado en Cowork (Nivel 3)
**"De carpeta caótica a entregable"**

1. Abre Cowork y dale acceso a una carpeta con archivos reales (facturas, reportes, notas)
2. Delega el proyecto completo:
   ```
   Organiza esta carpeta: clasifica los archivos por tipo, extrae
   los datos clave de las facturas a un Excel, y hazme un resumen
   ejecutivo de lo que hay aquí y qué requiere mi atención.
   ```
3. Observa el loop del agente en acción: cómo planea, actúa, verifica
4. Convierte el resultado en tarea programada mensual

**Lo que practicas:** delegación real, supervisión de agentes, tareas programadas.

## P4 · Proyecto en Claude Code con agentes (Nivel 4)
**"Análisis de datos con equipo de especialistas"**

```bash
mkdir analisis-ventas && cd analisis-ventas
mkdir -p datos resultados .claude/agents
cp ~/Descargas/ventas.csv datos/
claude
```

Dentro de la sesión:

```
> /init
> Explora @datos/ventas.csv y dime qué análisis serían valiosos
```

Crea dos subagentes en `.claude/agents/`: un `revisor-de-datos` (valida antes de analizar) y un `redactor` (formato oficial de reportes). Luego:

```
> Usa el revisor-de-datos para validar @datos/. Cuando esté limpio,
  haz el análisis completo (tendencias, top productos, comparativas
  con gráficas) y que el redactor genere el reporte en /resultados.
  Muéstrame tu plan antes de ejecutar.
```

**Lo que practicas:** carpeta de trabajo, CLAUDE.md, subagentes, modo plan.

## P5 · Proyecto automatizado con loop (Nivel 4 avanzado)
**"El reporte que se hace solo — con verificación"**

Ingredientes: la Skill de reportes (P2/4.4) + subagentes (P4) + `claude -p` + el programador de tareas de tu sistema.

```bash
# 1. Prueba manual con criterio verificable y tope de intentos:
cd ~/analisis-ventas
claude -p "Ejecuta la skill reporte-semanal. Verifica que el reporte
incluya las 4 secciones obligatorias y que las cifras cuadren con los
CSV fuente. Si algo falla, corrígelo y vuelve a verificar. Máximo 5
intentos; si no lo logras, deja un archivo PENDIENTES.md explicando qué faltó."

# 2. Si funciona, prográmalo (Mac/Linux, lunes 7:00 am):
crontab -e
# agrega:
0 7 * * 1 cd ~/analisis-ventas && claude -p "Ejecuta la skill reporte-semanal [misma instrucción completa]"
```

Nota cómo esta instrucción contiene los 4 ingredientes del loop: objetivo, verificación, condición de parada (5 intentos) y memoria en disco (PENDIENTES.md).

**Lo que practicas:** diseño de loops con verificación, automatización responsable con topes.

## Buenas prácticas transversales (para cualquier proyecto)

1. **Una carpeta por proyecto**, siempre
2. **Contexto primero:** CLAUDE.md, archivos relevantes, instrucciones claras
3. **Plan antes de ejecución** en tareas grandes
4. **Revisa los cambios** antes de confiar ciegamente
5. **Regla del 3:** instrucción repetida 3 veces → Skill
6. **Rol que usas seguido → agente** (revisor, redactor, analista)
7. **Flujo que funciona y se repite → tarea programada**
8. **Todo loop lleva verificación, tope de intentos y checkpoint humano en lo delicado**
9. **Verifica los datos importantes.** Siempre.

---
---

# 🎓 TAREA FINAL INTEGRADORA
## "Diseña tu primera automatización (en papel)"

Esta tarea no requiere ejecutar nada técnico — se puede hacer con papel y pluma — pero obliga a aplicar **todo el mapa del curso** a tu vida real. Entregable: **1 página**.

### Los 7 pasos

**1. Elige UNA tarea repetitiva real** de tu trabajo o tu vida, que hagas al menos una vez por semana.

**2. Descríbela como la haces HOY:** pasos, tiempo que te toma, herramientas que usas, y qué es lo que más te frustra de ella.

**3. Ubícala en la escalera:** ¿cuál es el nivel MÍNIMO que la resuelve? (¿Basta el chat con un buen prompt? ¿Necesita conectores? ¿Es un proyecto delegable a Cowork? ¿Requiere Claude Code?) Justifica en 2 líneas.

**4. Diseña las piezas:**
- ¿Qué conectores (MCP) necesita? (correo, calendario, archivos, otra app)
- Escribe la **Skill** que le enseñaría tu manera de hacerla — máximo 10 líneas
- Si necesita agentes, nombra los roles (ej. investigador, revisor, redactor)

**5. Define la verificación:** ¿cómo se comprueba que el resultado está bien? ¿Contra qué se compara? (criterios, fuente de verdad, formato obligatorio). *Recuerda: el verificador es el cuello de botella.*

**6. Define la condición de parada y el checkpoint humano:** tope de intentos, y la lista de acciones que SIEMPRE requieren tu aprobación antes de ejecutarse.

**7. Plan de adopción en 3 fases:**
- **Fase 1 (2 semanas):** manual asistido — tú la haces CON la IA, cada vez
- **Fase 2:** delegada supervisada — la IA la hace, tú revisas cada entregable
- **Fase 3:** programada — corre sola en horario, tú revisas por muestreo

### Autoevaluación: tu diseño está listo si puedes responder SÍ a todo

| ✔ | Pregunta |
|---|---|
| ☐ | ¿La tarea es concreta y real (no hipotética)? |
| ☐ | ¿El nivel elegido es el mínimo necesario y está justificado? |
| ☐ | ¿La Skill cabe en 10 líneas y una persona nueva la entendería? |
| ☐ | ¿La verificación es medible (no "que quede bien")? |
| ☐ | ¿Hay tope de intentos y checkpoint humano para lo delicado? |
| ☐ | ¿El plan de adopción es gradual (manual → supervisado → programado)? |

> 💬 **Para el instructor:** esta tarea funciona muy bien compartida en grupo — 3 minutos por persona presentando su diseño. Los participantes se roban ideas entre sí, y eso es exactamente lo que queremos.

---
---

# 📖 GLOSARIO COMPLETO DE REFERENCIA
*Ordenado por nivel, de lo fundamental a lo avanzado.*

### Nivel 1 — Entender y conversar

| Término | Definición en una línea |
|---|---|
| **LLM** | El "cerebro": modelo entrenado con enormes cantidades de texto que genera respuestas prediciendo lenguaje |
| **Token** | La unidad de texto (y de costo) con la que trabaja la IA; ~¾ de palabra en promedio |
| **Ventana de contexto** | La "memoria de trabajo": el máximo de tokens que la IA puede tener presentes a la vez |
| **Modelo** | Cada versión del cerebro con distinta potencia/velocidad/costo (Haiku, Sonnet, Opus...) |
| **Alucinación** | Cuando la IA inventa información que suena correcta pero es falsa; se combate verificando |
| **Fecha de corte** | El límite temporal del conocimiento de entrenamiento del modelo |
| **Chat con IA** | La forma básica de uso: conversación de ida y vuelta |
| **Prompt** | La instrucción que le das a la IA |
| **Prompt engineering** | Técnicas para escribir instrucciones que producen mejores resultados |
| **Few-shot** | Técnica de incluir ejemplos en el prompt para guiar el formato y estilo |
| **Búsqueda web** | Capacidad de la IA de buscar en internet en tiempo real y citar fuentes |
| **RAG** | Técnica de conectar la IA a TUS documentos para que responda basándose en ellos ("examen a libro abierto") |

### Nivel 2 — Conectar y potenciar

| Término | Definición en una línea |
|---|---|
| **MCP** | Estándar universal ("USB-C de la IA") para conectar la IA con apps y servicios |
| **Servidor MCP / Conector** | Cada conexión individual: el de Gmail, el de Canva, el de tu base de datos |
| **Skill** | Manual de procedimientos reutilizable (carpeta con SKILL.md) que enseña a la IA a hacer una tarea a tu manera |
| **Plugin** | Paquete instalable que agrupa skills + comandos + agentes + conexiones MCP |
| **API** | La "puerta de servicio" por la que cualquier programa puede usar a la IA directamente |

### Nivel 3 — Delegar trabajo

| Término | Definición en una línea |
|---|---|
| **Agente** | IA que planea, usa herramientas y ejecuta pasos hasta cumplir un objetivo |
| **Loop del agente** | El ciclo universal: observar → planear → actuar → verificar → repetir |
| **Subagente** | Agente especializado al que el principal le delega una parte del trabajo |
| **Cowork** | App de escritorio de Claude para delegar proyectos completos de oficina |
| **Tarea programada** | Instrucción que se ejecuta automáticamente en un horario definido |

### Nivel 4 — Construir sistemas

| Término | Definición en una línea |
|---|---|
| **Claude Code** | Claude en tu terminal: trabaja en tus carpetas reales y ejecuta comandos |
| **Terminal** | La ventana de línea de comandos de tu computadora |
| **Carpeta de trabajo** | La "oficina" del proyecto: Claude Code opera desde donde lo ejecutas |
| **CLAUDE.md** | Archivo de instrucciones del proyecto que Claude Code lee automáticamente al iniciar |
| **Slash command** | Comando dentro de la sesión que empieza con `/` (`/init`, `/plan`, `/goal`...) |
| **`claude -p`** | Modo "una sola orden": ejecuta y termina; la base de la automatización |
| **Hook** | Regla automática "cuando pase X, haz Y"; garantía que se ejecuta siempre |
| **Loop** | Una tarea con verificación corriendo sola: hacer → verificar → ¿continuar o parar? |
| **Loop engineering** | Diseñar los sistemas/loops que instruyen a los agentes, en vez de escribir cada prompt |
| **Context engineering** | Preparar deliberadamente todo el contexto (archivos, skills, herramientas) para la tarea |
| **Verificador** | El mecanismo que comprueba si el trabajo del loop está bien; el cuello de botella de todo el sistema |
| **Condición de parada** | El criterio que detiene un loop: éxito verificado o límite de intentos |

---

# 🗺️ MAPA DE DECISIÓN FINAL

## ¿Qué opción uso para mi proyecto?

```
                    ¿QUÉ QUIERO HACER?
                            │
   ┌────────────┬───────────┼───────────────┬───────────────┐
   │            │           │               │               │
Preguntar,   Lo mismo,   Delegar un     Trabajar a      Que suceda
redactar,    pero con    proyecto       fondo en mis    solo, sin mí,
analizar     MIS datos   completo       archivos, con   con verificación
algo         y apps      de oficina     máximo control
   │            │           │               │               │
   ▼            ▼           ▼               ▼               ▼
 CHAT        CHAT +      COWORK        CLAUDE CODE     TAREAS PROGRAMADAS
(Nivel 1)    MCP/Skills  (Nivel 3)     (Nivel 4)       + LOOPS
             (Nivel 2)                                  (Niveles 3-4)

   Y en TODOS los niveles puedes potenciar con:
   ├── MCP      → conectar tus herramientas
   ├── SKILLS   → enseñarle TU forma de hacer las cosas
   ├── AGENTES  → dividir el trabajo entre especialistas
   └── PLUGINS  → instalar capacidades ya hechas
```

## La idea final del curso

> El chat es solo la puerta de entrada. La productividad real llega cuando dejas de *preguntarle* cosas a la IA y empiezas a *delegarle* trabajo: con acceso a tus herramientas (MCP), con tus procedimientos (Skills), dividido entre especialistas (agentes), y eventualmente corriendo solo con verificaciones bien diseñadas (loops). Y la habilidad más valiosa en todo este camino no es técnica: es **tu criterio para definir qué significa "bien hecho" y "terminado"**. Eso no lo automatiza nadie.

---

*Fuentes y documentación de referencia:*
- *Claude Code: https://docs.claude.com/en/docs/claude-code/overview*
- *API de Anthropic: https://docs.claude.com/en/api/overview*
- *Soporte de Claude.ai: https://support.claude.com*
- *Novedades: https://www.anthropic.com/news*
- *Sobre loops y trabajo agéntico de larga duración (Anthropic): https://www.anthropic.com/research/long-running-Claude*
- *Declaraciones de Boris Cherny (creador de Claude Code) sobre loops: conferencia @Scale de Meta, junio 2026*
