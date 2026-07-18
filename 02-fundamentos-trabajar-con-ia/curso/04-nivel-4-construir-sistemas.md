# 🔴 NIVEL 4 — CONSTRUIR SISTEMAS
*El máximo control: la IA en tu computadora, procesos automáticos y la frontera de los loops.*

## 4.1 Claude Code: la IA en tu computadora

**Claude Code** es Claude funcionando **dentro de tu terminal** (la línea de comandos). A pesar del nombre, no es solo para programadores: es la opción de **máximo poder y control**, porque le da a Claude:

- 📁 Acceso a tus **carpetas y archivos reales** (los que autorices)
- ⚙️ Capacidad de **ejecutar programas y comandos**
- 🔧 Todo lo anterior del curso: **agentes, Skills, MCP, plugins**, en su forma más configurable

### ¿Cuándo elegir Claude Code en vez de Cowork?

| Elige Cowork si... | Elige Claude Code si... |
|---|---|
| Quieres delegar sin configurar nada | Quieres controlar y personalizar cada pieza |
| Tus proyectos son documentos y análisis de oficina | Tus proyectos involucran datos masivos, código o automatización profunda |
| La terminal te intimida (por ahora) | Quieres construir flujos reutilizables y loops |

### Instalación (paso a paso)

**Requisito:** cuenta de Claude (Pro, Max, Team o Enterprise) o acceso a la API.

```bash
# 1. Abre tu terminal
#    Mac: app "Terminal" · Windows: WSL · Linux: cualquiera

# 2. Instala (método recomendado Mac/Linux/WSL):
curl -fsSL https://claude.ai/install.sh | bash

#    Alternativa con npm (requiere Node.js):
npm install -g @anthropic-ai/claude-code

# 3. Verifica:
claude --version

# 4. Si algo falla, diagnostica:
claude doctor
```

La primera vez que ejecutes `claude`, se abre el navegador para iniciar sesión. Listo.

> 📖 Documentación oficial: https://docs.claude.com/en/docs/claude-code/overview

> 🎯 **Hazlo tú ahora (3-5 min):** instala Claude Code y corre `claude --version` y `claude doctor`. Nada más. Ese pequeño triunfo de terminal derriba la barrera psicológica más grande del Nivel 4.
>
> ⚠️ **Error común:** ejecutar `claude` desde la carpeta raíz o el escritorio, dándole visibilidad de TODO. Poder sin foco.
>
> ✅ **Buena práctica:** siempre desde la carpeta del proyecto, y lee qué permiso te pide antes de aprobar cada cambio. Esa pausa de 2 segundos es tu cinturón de seguridad.


---

## 4.2 La carpeta de trabajo y el archivo CLAUDE.md

### La regla de oro de la carpeta

> **Claude Code trabaja en la carpeta desde donde lo ejecutas.** Esa carpeta es su "oficina": ahí lee, ahí crea, ahí modifica — y te pide permiso antes de cambiar cosas.

```bash
mkdir mi-proyecto        # 1. crea la carpeta del proyecto
cd mi-proyecto           # 2. entra a ella
cp ~/Descargas/datos.csv .   # 3. copia ahí tus archivos de trabajo
claude                   # 4. inicia Claude Code DESDE esa carpeta
```

**Por qué importa:** seguridad (solo ve esa carpeta), orden (un proyecto = una carpeta) y contexto (explora la carpeta para entender tu proyecto).

### Estructura recomendada

```
mi-proyecto/
├── CLAUDE.md          ← las instrucciones del proyecto
├── datos/             ← archivos de entrada
├── resultados/        ← lo que Claude genera
└── .claude/           ← configuración avanzada (skills, agentes, hooks)
```

### CLAUDE.md: la hoja de bienvenida del proyecto

`CLAUDE.md` es un archivo de texto en la raíz de tu carpeta que Claude Code **lee automáticamente al iniciar cada sesión**. Sin él, Claude adivina; con él, Claude sabe.

**Qué debe contener:** contexto del proyecto, qué hay en cada carpeta, tus reglas de trabajo y los comandos frecuentes.

**Ejemplo para un proyecto NO técnico:**

```markdown
# Proyecto: Análisis mensual de ventas

## Contexto
Cada mes analizo las ventas y preparo un reporte para dirección.
Los datos llegan como CSV.

## Estructura
- /datos → los CSV crudos de cada mes
- /resultados → reportes y gráficas generados

## Reglas de trabajo
- Todo en español, cifras en $1,234.56 MXN
- Reportes: resumen ejecutivo, tendencias, comparación vs mes
  anterior, recomendaciones. Máximo 2 páginas.
- Antes de borrar o sobrescribir archivos, pregúntame
- Todos los entregables van a /resultados
```

**Ejemplo para un proyecto técnico:**

```markdown
# Mi App

## Stack
- Python 3.11, FastAPI, PostgreSQL 16, tests con pytest

## Comandos
- `source venv/bin/activate` antes de cualquier comando Python
- `pytest -v` corre las pruebas

## Reglas
- Type hints en todas las funciones
- Después de cada cambio, corre las pruebas
```

**Cómo crearlo:** o lo escribes tú con cualquier editor, o dentro de la sesión escribes `/init` y Claude explora la carpeta y lo genera por ti.

> **Regla de oro:** corto y claro gana. Un CLAUDE.md de ~30 líneas bien pensadas funciona mejor que uno de 300 que nadie mantiene. Es un índice, no una enciclopedia.

> 🎯 **Hazlo tú ahora (3-5 min):** crea una carpeta de práctica con 2-3 archivos cualquiera, entra, ejecuta `claude` y escribe `/init`. Lee el CLAUDE.md que genera y ajústale 3 líneas a tu gusto.
>
> ⚠️ **Error común:** los dos extremos: no tener CLAUDE.md (Claude adivina todo) o tener una enciclopedia de 300 líneas que nadie actualiza (Claude se pierde).
>
> ✅ **Buena práctica:** ~30 líneas vivas. Incluye siempre "antes de borrar o sobrescribir, pregúntame". Y cada vez que corrijas a Claude dos veces por lo mismo → esa regla va al CLAUDE.md.


---

## 4.3 Trabajar desde la terminal: comandos esenciales

### Las dos formas de usar Claude Code

```bash
# 1. Modo interactivo (el normal): abres sesión y trabajas
claude

# 2. Modo de una sola orden (base de la automatización):
claude -p "Resume todos los PDFs de datos/ en un archivo resumen.md"
```

### Comandos dentro de la sesión (slash commands)

Escribe `/` y verás la lista completa. Los esenciales:

**Sesión y contexto** *(directamente conectados con lo que viste en 1.2)*

| Comando | Qué hace |
|---|---|
| `/init` | Genera el CLAUDE.md explorando la carpeta |
| `/clear` | Limpia el "escritorio": conversación nueva, mismo proyecto |
| `/compact` | Comprime la conversación larga conservando lo importante |
| `/context` | Muestra cuánta ventana de contexto llevas usada |
| `/resume` | Retoma una sesión anterior |
| `/rewind` | Regresa a un punto anterior (deshacer) |

**Planeación y control**

| Comando | Qué hace |
|---|---|
| `/plan` | Modo plan: Claude propone QUÉ hará antes de hacerlo, tú apruebas |
| `/diff` | Muestra exactamente qué cambió en los archivos |
| `/model` | Cambia de modelo (¿recuerdas 1.3? aquí lo aplicas) |
| `/cost` | Muestra el consumo de la sesión |
| `/help` | Lista todos los comandos |

**Herramientas**

| Comando | Qué hace |
|---|---|
| `/mcp` | Gestiona tus servidores MCP |
| `/agents` | Gestiona tus subagentes |
| `/plugins` | Gestiona tus plugins |

### El truco del @

Menciona archivos directamente en lugar de copiar y pegar:

```
> Analiza @datos/ventas-enero.csv y compáralo con @datos/ventas-diciembre.csv
```

> 🎯 **Hazlo tú ahora (3-5 min):** dentro de una sesión escribe `/help` y luego `/context`. Familiarízate con 3 comandos hoy; los demás llegarán cuando los necesites.
>
> ⚠️ **Error común:** lanzar una tarea grande sin `/plan` y sorprenderse del rumbo que tomó. El modo plan existe exactamente para eso.
>
> ✅ **Buena práctica:** el trío de control: `/plan` para lo grande, `/diff` antes de confiar, `/clear` al cambiar de tema.


---

## 4.4 MCP, Skills, agentes y plugins desde la terminal

Todo el Nivel 2 y 3 vive también aquí, en su forma más configurable.

### MCP

```bash
claude mcp add <nombre> <comando>    # conectar un servidor
claude mcp list                      # ver conectados
claude mcp remove <nombre>           # quitar
```

Una vez conectado, lo usas en lenguaje natural dentro de la sesión:

```
> Consulta en la base de datos cuántos clientes nuevos hubo este mes
```

### Skills

Viven en carpetas:

```
.claude/skills/       ← skills de ESTE proyecto (compartibles con tu equipo)
~/.claude/skills/     ← tus skills PERSONALES (todos tus proyectos)
```

Crear una:

```bash
mkdir -p .claude/skills/reporte-semanal
# crea dentro el archivo SKILL.md (formato de la sección 2.2)
```

Usarla: `/reporte-semanal` como comando, o simplemente pídelo en lenguaje natural y Claude la activa solo.

> 💡 Nota: los "custom commands" antiguos vivían en `.claude/commands/`. Siguen funcionando, pero el formato recomendado hoy es el de Skills (`.claude/skills/<nombre>/SKILL.md`).

### Subagentes

```
.claude/agents/       ← agentes de este proyecto
~/.claude/agents/     ← agentes personales
```

Cada agente es un archivo markdown con su especialidad:

```markdown
---
name: revisor-de-datos
description: Verifica calidad y consistencia de datos antes de cualquier análisis
tools: Read, Grep, Bash
---

Eres un revisor de calidad de datos. Cuando recibas archivos:
1. Verifica que no haya filas vacías o duplicadas
2. Confirma formatos válidos de fechas y montos
3. Reporta anomalías ANTES de que se use el dato
```

Se usan en lenguaje natural ("usa el agente revisor-de-datos para validar /datos") o Claude les delega solo cuando su descripción coincide con la tarea. Pueden correr **varios en paralelo**.

### Plugins

`/plugins` dentro de la sesión: instala paquetes que agregan de golpe skills, comandos, agentes y conexiones MCP.

> 🎯 **Hazlo tú ahora (3-5 min):** crea tu primera skill de proyecto: lleva la que escribiste en el Nivel 2 a `.claude/skills/` de tu carpeta de práctica y pruébala con una petición en lenguaje natural.
>
> ⚠️ **Error común:** guardar skills personales dentro de un proyecto específico (las pierdes al cambiar de proyecto) o skills del equipo en tu carpeta personal (nadie más las tiene).
>
> ✅ **Buena práctica:** lo personal vive en `~/.claude/`; lo del proyecto o equipo vive en `.claude/` de la carpeta compartida.


---

## 4.5 Hooks: reacciones automáticas

### La explicación sencilla

Un **hook** ("gancho") es una regla del tipo **"cuando pase X, haz Y automáticamente"**. Se configuran en `.claude/settings.json` y se disparan ante eventos de la sesión.

### La analogía: las puertas automáticas 🚪

No le pides a la puerta que se abra: se abre sola cuando detecta que te acercas. Un hook es eso: una reacción automática ante un evento, sin que nadie la pida.

### Ejemplos de hooks

| Cuando pase esto... | ...haz esto automáticamente |
|---|---|
| Claude edite cualquier archivo | Formatea el archivo con la herramienta de estilo |
| Claude termine una tarea | Envía una notificación |
| Claude vaya a ejecutar un comando delicado | Pide confirmación extra o bloquéalo |
| Claude modifique datos | Haz respaldo del archivo original primero |

### Por qué importan

Los hooks son **garantías, no sugerencias**. Una instrucción en CLAUDE.md la IA podría pasarla por alto; un hook se ejecuta **siempre**. Son la pieza que convierte "confío en que lo haga" en "el sistema lo garantiza" — esencial cuando empiezas a automatizar en serio (siguiente sección).

> 🎯 **Hazlo tú ahora (3-5 min):** piensa la regla "cuando pase X, haz Y" que más tranquilidad te daría en tu trabajo (un respaldo, un bloqueo, una alerta). Escríbela en papel: ya diseñaste tu primer hook.
>
> ⚠️ **Error común:** confiar reglas críticas de seguridad solo a texto en CLAUDE.md. Las instrucciones se pueden pasar por alto; los hooks no.
>
> ✅ **Buena práctica:** lo crítico va en hooks (garantía que se ejecuta siempre); lo estilístico va en CLAUDE.md (guía que orienta).


---

## 4.6 Loops: la frontera actual (lo que dice el creador de Claude Code)

Llegamos a la cima de la escalera: el concepto más avanzado del curso y la conversación más caliente de la industria en 2026.

### El contexto: qué está pasando

**Boris Cherny**, ingeniero de Anthropic y **creador de Claude Code**, ha declarado públicamente en 2026 (incluida su participación en la conferencia @Scale de Meta, en junio) que el siguiente salto después de los agentes son los **loops**: sistemas donde los agentes les dan instrucciones a otros agentes, corriendo de forma continua, con mínima intervención humana.

Su forma de describir su propio trabajo lo resume todo: dice que ya casi no escribe prompts él mismo — tiene loops corriendo que le dan instrucciones a Claude y deciden qué sigue; su trabajo ahora es **diseñar esos loops**. O en su formulación más citada: "You're supposed to build a system that prompts itself" (*se supone que construyas un sistema que se instruye a sí mismo*).

Cherny ubica esto en una evolución de tres etapas: primero los humanos escribían el código → luego los agentes escriben el código → ahora **los agentes instruyen a los agentes** que hacen el trabajo.

### La escalera de habilidades (importantísima para entender tu propio aprendizaje)

```
2023 → PROMPT ENGINEERING     "Escribo bien la instrucción"        (tu Nivel 1)
2024-25 → CONTEXT ENGINEERING "Preparo bien todo el contexto:      (tus Niveles 2-3)
                               archivos, skills, herramientas"
2026 → LOOP ENGINEERING       "Diseño el sistema que genera        (Nivel 4, la frontera)
                               sus propias instrucciones"
```

**Ojo:** cada capa envuelve a la anterior, no la reemplaza. Un mal prompt dentro de un loop solo produce basura más rápido. Por eso este curso empezó por los fundamentos.

### ¿Qué es exactamente un loop?

Ya conoces el **loop del agente** (sección 3.2): observar → planear → actuar → verificar → repetir. Un **loop** en este sentido nuevo es ese ciclo **corriendo solo, sin ti adentro**.

La definición más simple que circula en la industria:

> **Un loop es una tarea con una verificación.** Haz algo → comprueba el resultado → decide si continuar o parar.

Antes, **tú eras el loop**: leías cada respuesta, detectabas errores, decidías el siguiente paso, volvías a pedir. *Loop engineering* es salirte de ese ciclo y subirte un nivel: en vez de dar cada instrucción, **diseñas la pista por la que el agente corre solo**.

### Los 4 ingredientes de un loop bien diseñado

Aquí se concentra todo el aprendizaje práctico. Un loop necesita:

```
1. OBJETIVO claro           →  "Que todos los datos del mes queden
                                validados y el reporte generado"

2. VERIFICACIÓN real        →  ¿Cómo se comprueba que está bien?
                                (revisar contra criterios, correr
                                pruebas, comparar con la fuente)

3. CONDICIÓN DE PARADA      →  ¿Cuándo termina? "Cuando pase la
                                verificación" + un límite de
                                intentos ("máximo 10 vueltas")

4. MEMORIA fuera del loop   →  El progreso se guarda en archivos
                                en disco, porque el contexto de
                                cada vuelta se reinicia (¡1.2!)
```

**La lección central que repiten los practicantes:** el cuello de botella no es el modelo, es **el verificador**. Un loop con verificación débil no produce trabajo excelente: produce mediocridad en volumen. Y una trampa conocida: si el mismo agente que hizo el trabajo lo califica, siempre se pondrá buena nota — por eso los buenos diseños **separan al agente que hace del agente que evalúa** (¿recuerdas los subagentes de 3.3?).

### Cómo se ve en la práctica (sin misticismo)

En Claude Code ya existen mecanismos nativos y patrones para esto:

- **`/goal`** — le das un objetivo y una condición verificable, y Claude sigue trabajando turno tras turno hasta cumplirla
- **`/loop`** y patrones como el **"Ralph loop"** (instalable vía `/plugin`) — reinsertan al agente en la tarea cuando dice "ya terminé", preguntándole si *de verdad* cumplió el criterio; útil porque los modelos a veces sufren "pereza agéntica" y dan por terminado algo incompleto
- **Tareas programadas + `claude -p`** — el latido del sistema: loops que despiertan solos en horario (une 3.5 con 4.3)

Un ejemplo sencillo y honesto de loop:

```
Objetivo: que la carpeta /datos quede limpia y validada.
Loop:     revisa los archivos → detecta problemas → corrígelos →
          vuelve a validar.
Para:     cuando la validación pase completa, o tras 6 intentos
          (entonces repórtame qué quedó pendiente).
```

### Las advertencias (tan importantes como la promesa)

1. **Costo sin techo.** Un loop, por diseño, sigue corriendo. Sin límites de iteraciones y presupuesto, la factura crece mientras duermes. Siempre pon topes.
2. **La máquina de mediocridad.** Loop + verificador débil = volumen de trabajo malo a gran velocidad. Invierte más en definir "qué es un buen resultado" que en el loop mismo.
3. **Puntos de control humanos.** Para acciones delicadas (borrar, enviar, publicar, pagar), el loop debe detenerse y pedir aprobación. Los hooks (4.5) son tus aliados aquí.
4. **Empieza minúsculo.** Tu primer loop debe ser de bajo riesgo: validar datos, generar borradores, ordenar archivos. Nunca empieces automatizando lo crítico.

### Por qué te cuento esto aunque estés empezando

Porque define **hacia dónde va tu curva de aprendizaje**. Hoy escribes prompts; mañana prepararás contextos, skills y agentes; y el horizonte es diseñar los sistemas que trabajan solos. La habilidad escasa ya no es escribir la instrucción — es **definir qué significa "bien hecho" y "terminado"**. Y esa habilidad es puro criterio profesional humano: el tuyo.

> 🎯 **Hazlo tú ahora (3-5 min):** toma la tarea programada que diseñaste en 3.5 y conviértela en loop: agrégale los 4 ingredientes (objetivo, verificación, tope de intentos, memoria en disco). En papel basta.
>
> ⚠️ **Error común:** el loop sin tope de intentos ni presupuesto: amanecer con una factura enorme por un ciclo que giró toda la noche sin avanzar. Pasa, y pasa de verdad.
>
> ✅ **Buena práctica:** verificador separado del hacedor, topes siempre, y checkpoint humano obligatorio para toda acción delicada (borrar, enviar, publicar, pagar).


---

### ✅ Checkpoint del Nivel 4

Sabes qué es Claude Code y cuándo elegirlo, dominas la carpeta de trabajo y CLAUDE.md, conoces los comandos esenciales, sabes dónde viven MCP/Skills/agentes/plugins en la terminal, entiendes los hooks como garantías automáticas, y conoces la frontera: los loops. **Tienes el mapa completo.** Ahora, a practicar.

---
---
