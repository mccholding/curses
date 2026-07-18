# Curso Completo de Claude Code
## De lo básico a lo avanzado: agentes, skills, MCP, plugins y automatización

> **Audiencia:** desarrolladores con conocimientos básicos de terminal y Git.
> **Duración sugerida:** 12 módulos (1 sesión de 2–3 horas por módulo + tarea).
> Los módulos 9–12 incluyen ejemplos de soluciones empresariales y un caso práctico evaluable.
> **Documentación oficial:** https://code.claude.com/docs/en/overview
> Cada módulo incluye: objetivos, contenido, práctica guiada en clase y tarea evaluable.

---

## Módulo 1 — Fundamentos

### Objetivos
- Instalar Claude Code y autenticarse.
- Entender el loop agéntico (cómo Claude lee, planea, edita y verifica).
- Abrir Claude Code en la carpeta correcta y ejecutar los comandos esenciales.

### Contenido

**1.1 Instalación**

macOS / Linux / WSL:
```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Windows (PowerShell):
```powershell
irm https://claude.ai/install.ps1 | iex
```

También existe instalación vía npm (`npm install -g @anthropic-ai/claude-code`) y Homebrew. Verifica con:
```bash
claude --version
claude doctor
```
Docs: https://code.claude.com/docs/en/setup

**1.2 Abrir Claude Code en la carpeta correcta (¡clave!)**

Claude Code trabaja sobre el directorio donde lo inicias. Ese directorio define qué archivos puede leer/editar y qué CLAUDE.md carga:

```bash
cd ~/proyectos/mi-app     # 1. navega a tu proyecto
claude                    # 2. inicia la sesión interactiva ahí
```

Reglas prácticas:
- En un monorepo, inicia en el paquete donde vas a trabajar, no siempre en la raíz.
- Puedes dar acceso a carpetas extra con `claude --add-dir ../otro-paquete`.
- Nunca inicies en `~` o `/`: contexto gigante y riesgo innecesario.

**1.3 El loop agéntico**

Claude Code no es un chat: es un agente que en cada turno puede leer archivos, ejecutar comandos, editar código y verificar resultados, repitiendo el ciclo hasta cumplir la tarea. Tú apruebas las acciones sensibles mediante permisos.
Docs: https://code.claude.com/docs/en/how-claude-code-works

**1.4 Comandos esenciales de arranque**

| Comando | Qué hace |
|---|---|
| `claude` | Sesión interactiva |
| `claude "arregla el bug X"` | Inicia con un prompt |
| `claude -c` | Continúa la última conversación |
| `claude -r` | Reanuda una sesión anterior (selector) |
| `/help` | Lista comandos disponibles |
| `/init` | Genera un CLAUDE.md inicial del proyecto |
| `/clear` | Limpia el contexto |
| `/model` | Cambia de modelo |
| `Esc` | Interrumpe a Claude a mitad de tarea |

### Práctica guiada (en clase)
1. Clonar un repo pequeño de ejemplo (cualquier app con tests).
2. `cd` al repo, ejecutar `claude` y preguntar: *"Dame un resumen de la arquitectura de este proyecto y sus archivos principales"*.
3. Pedir: *"Explica qué hace la función X del archivo Y"*.
4. Hacer un primer cambio trivial (corregir un typo en el README) y observar el flujo de permisos.

### Tarea para alumnos
> **Entregable:** captura de pantalla o transcript + respuestas escritas.
1. Instala Claude Code y ejecuta `claude doctor`.
2. En un proyecto propio, corre `/init` y revisa el CLAUDE.md generado.
3. Pide a Claude que explique el proyecto y que corrija un bug pequeño real.
4. Responde: ¿qué herramientas usó Claude (Read, Bash, Edit…)? ¿En qué momento te pidió permiso y por qué?

---

## Módulo 2 — Uso correcto en el día a día

### Objetivos
- Dominar CLAUDE.md, memoria y reglas.
- Usar modos de permisos y plan mode.
- Gestionar sesiones, checkpoints y contexto.
- Aplicar las buenas prácticas oficiales.

### Contenido

**2.1 CLAUDE.md y memoria**

CLAUDE.md es el archivo de instrucciones que Claude carga automáticamente al iniciar en una carpeta. Úsalo para: comandos del proyecto (build, test, lint), convenciones de código, arquitectura y advertencias ("no toques la carpeta legacy/").

Ubicaciones:
- `./CLAUDE.md` → instrucciones del proyecto (se versiona en git).
- `~/.claude/CLAUDE.md` → instrucciones personales globales.
- `.claude/rules/` → reglas organizadas por tema o por ruta.
- `/memory` → ver y editar la memoria desde la sesión.

Consejo: escribe instrucciones cortas, concretas y verificables. "Usa pnpm, nunca npm" funciona mejor que párrafos largos.
Docs: https://code.claude.com/docs/en/memory

**2.2 Modos de permisos**

Cambia de modo con `Shift+Tab` o `/permissions`:
- **default** — pregunta antes de acciones sensibles.
- **acceptEdits** — auto-aprueba ediciones de archivos.
- **plan** — Claude solo lee y analiza; produce un plan que tú apruebas antes de que toque código. Ideal para refactors grandes.
- **auto / bypassPermissions** — mínima fricción; úsalo solo en entornos aislados.

Docs: https://code.claude.com/docs/en/permission-modes

**2.3 Sesiones, checkpoints y contexto**
- `claude -c` / `claude -r` para continuar o reanudar.
- `/rewind` — vuelve a un checkpoint anterior (deshace cambios de Claude).
- `/compact` — resume la conversación cuando el contexto se llena.
- `/context` — visualiza qué está ocupando tu ventana de contexto.

**2.4 Buenas prácticas oficiales**
1. **Explora → planea → codifica**: pide primero que investigue, luego un plan (plan mode), luego la implementación.
2. **Dale forma de verificar su trabajo**: tests, un comando de build, una captura esperada. Claude itera mucho mejor cuando puede comprobar si acertó.
3. **Sé específico**: "arregla el login" ❌ vs "el login falla con emails con mayúsculas; el test está en tests/auth.test.ts" ✅.
4. **Corrige temprano**: interrumpe con `Esc` en cuanto veas que va por mal camino.
Docs: https://code.claude.com/docs/en/best-practices

### Práctica guiada
1. Activar plan mode y pedir un plan para un refactor real del repo de clase.
2. Revisar el plan, pedir un ajuste, aprobar y dejar que implemente.
3. Provocar un mal cambio a propósito y recuperarlo con `/rewind`.

### Tarea para alumnos
> **Entregable:** el CLAUDE.md + transcript del refactor.
1. Escribe un CLAUDE.md completo para un proyecto tuyo (comandos, convenciones, arquitectura, prohibiciones).
2. Ejecuta un refactor usando el flujo explora → plan mode → implementación, exigiendo que corra los tests al final.
3. Documenta: ¿el CLAUDE.md cambió el comportamiento de Claude? Da 2 ejemplos concretos.

---

## Módulo 3 — Personalización: settings, slash commands, output styles y hooks

### Objetivos
- Entender la jerarquía de configuración y el directorio `.claude/`.
- Crear slash commands personalizados.
- Crear un primer hook de automatización.

### Contenido

**3.1 El directorio `.claude/` y settings**

| Archivo | Alcance |
|---|---|
| `~/.claude/settings.json` | Usuario (todas tus sesiones) |
| `.claude/settings.json` | Proyecto (se comparte con el equipo) |
| `.claude/settings.local.json` | Proyecto, solo tú (gitignored) |

En settings puedes definir permisos (`allow`/`deny` por herramienta), variables de entorno, hooks, modelo por defecto y más.
Docs: https://code.claude.com/docs/en/settings

**3.2 Slash commands personalizados**

Un slash command es un prompt reutilizable guardado en Markdown:

```
.claude/commands/revisar-pr.md        # del proyecto
~/.claude/commands/explicar.md        # personales
```

Ejemplo `.claude/commands/fix-issue.md`:
```markdown
---
description: Analiza y corrige un issue de GitHub
---
Analiza el issue #$ARGUMENTS con `gh issue view`,
localiza el código relevante, implementa la corrección,
corre los tests y prepara un commit descriptivo.
```
Uso: `/fix-issue 123`.

**3.3 Output styles**

Cambian la "personalidad" de las respuestas (por ejemplo, un estilo explicativo para enseñar). `/output-style` para cambiarlo, y puedes crear estilos propios.
Docs: https://code.claude.com/docs/en/output-styles

**3.4 Primer hook: auto-formatear tras cada edición**

Los hooks son comandos que se ejecutan en eventos del ciclo de vida (PreToolUse, PostToolUse, Stop, SessionStart…). En `.claude/settings.json`:

```json
{
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          { "type": "command", "command": "npx prettier --write \"$CLAUDE_FILE_PATHS\" 2>/dev/null || true" }
        ]
      }
    ]
  }
}
```

Otro clásico: bloquear ediciones a archivos protegidos con un hook PreToolUse que devuelve exit code 2 (bloquea la acción y le explica el motivo a Claude).
Docs: https://code.claude.com/docs/en/hooks-guide

> Este es solo el inicio: los hooks a nivel empresarial (auditoría, compliance, notificaciones) se profundizan en el **Módulo 9**.

### Práctica guiada
1. Crear `/test-y-commit`: comando que corre los tests y, si pasan, hace commit con mensaje convencional.
2. Configurar el hook de auto-formato y verlo actuar en vivo.
3. Explorar `/hooks` para inspeccionar los hooks activos.

### Tarea para alumnos
> **Entregable:** repo con `.claude/` versionado.
1. Crea 3 slash commands útiles para tu stack (ej.: `/nueva-migracion`, `/revisar-seguridad`, `/doc-funcion`), al menos uno con `$ARGUMENTS`.
2. Crea 2 hooks: uno de formato/lint automático y uno que bloquee ediciones a un archivo sensible (ej. `.env`).
3. Redacta un README corto explicando a un compañero cómo usar tu configuración.

---

## Módulo 4 — Skills

### Objetivos
- Entender qué es una skill y cuándo usarla en lugar de CLAUDE.md o un slash command.
- Crear skills con frontmatter y archivos de apoyo.
- Conocer patrones avanzados (skills en subagentes, contexto dinámico).

### Contenido

**4.1 Qué es una skill**

Una skill es una carpeta con un `SKILL.md` que enseña a Claude *cómo* hacer una tarea específica (proceso, convenciones, scripts de apoyo). A diferencia de CLAUDE.md (siempre cargado), las skills se cargan **solo cuando son relevantes**, lo que ahorra contexto.

**4.2 Dónde viven**
```
.claude/skills/<nombre>/SKILL.md    # del proyecto
~/.claude/skills/<nombre>/SKILL.md  # personales
```

**4.3 Anatomía de una skill**

`.claude/skills/generar-reporte/SKILL.md`:
```markdown
---
name: generar-reporte
description: Genera reportes semanales de ventas en PDF a partir del CSV de exportación. Usar cuando pidan reportes, resúmenes de ventas o análisis del CSV semanal.
---

# Generar reporte de ventas

## Proceso
1. Lee el CSV más reciente en data/exports/.
2. Calcula totales por región con scripts/aggregate.py.
3. Genera el PDF con la plantilla templates/reporte.html.

## Reglas
- Moneda siempre en MXN con 2 decimales.
- Si faltan datos de una región, márcala como "Sin datos", nunca la omitas.
```

Claves del `description`: describe **qué hace** y **cuándo activarla**; es lo que Claude usa para decidir si carga la skill. Puedes añadir archivos de apoyo (scripts, plantillas, docs) dentro de la carpeta y referenciarlos desde el SKILL.md.

**4.4 Patrones avanzados**
- **Skills en subagente:** ejecutar la skill aislada para no contaminar el contexto principal.
- **Contexto dinámico:** inyectar la salida de un comando en la skill.
- **Pre-aprobar herramientas** que la skill necesita para reducir prompts de permiso.
Docs: https://code.claude.com/docs/en/skills

**4.5 Skill vs slash command vs CLAUDE.md**
- CLAUDE.md → reglas siempre vigentes del proyecto.
- Slash command → prompt que TÚ invocas manualmente.
- Skill → conocimiento que CLAUDE invoca automáticamente cuando la tarea lo amerita.

### Práctica guiada
1. Crear la skill `commits-convencionales` que enseñe el formato de commits del equipo.
2. Pedir un commit y comprobar que la skill se activa sola.
3. Depurar con la sección "Skill not triggering" de la doc si no dispara.

### Tarea para alumnos
> **Entregable:** carpeta de la skill + evidencia de 3 activaciones.
1. Crea una skill no trivial de tu dominio (ej.: "crear endpoint REST con nuestras convenciones", "escribir tests con nuestra estructura", "generar componente UI del design system").
2. Debe incluir al menos un archivo de apoyo (script o plantilla).
3. Prueba 5 prompts: 3 que deberían activarla y 2 que no. Ajusta el `description` hasta que discrimine bien y documenta los cambios que hiciste.

---

## Módulo 5 — MCP: conectar Claude con el mundo exterior

### Objetivos
- Entender qué es Model Context Protocol.
- Instalar servidores MCP (HTTP, SSE, stdio) y manejar scopes.
- Autenticarse con OAuth y usar herramientas MCP en flujos reales.

### Contenido

**5.1 Qué es MCP**

MCP es un protocolo abierto que da a Claude herramientas externas: consultar bases de datos, leer issues de GitHub, revisar errores en Sentry, controlar Figma, etc. Un "servidor MCP" expone herramientas; Claude Code es el cliente.

**5.2 Instalar servidores**

```bash
# Servidor remoto HTTP
claude mcp add --transport http github https://api.githubcopilot.com/mcp/

# Servidor remoto SSE
claude mcp add --transport sse linear https://mcp.linear.app/sse

# Servidor local stdio (proceso en tu máquina)
claude mcp add postgres -- npx -y @bytebase/dbhub --dsn "postgresql://user:pass@localhost/mi_db"
```

Gestión: `claude mcp list`, `claude mcp get <nombre>`, `claude mcp remove <nombre>`, y dentro de la sesión `/mcp` (estado y autenticación OAuth).

**5.3 Scopes de instalación**
- **local** (por defecto): solo tú, solo en este proyecto.
- **project** (`--scope project`): se guarda en `.mcp.json` y se versiona para todo el equipo.
- **user** (`--scope user`): disponible en todos tus proyectos.

**5.4 Autenticación**

Para servidores que requieren login (GitHub, Sentry, Linear…), corre `/mcp` y sigue el flujo OAuth en el navegador. También puedes pasar tokens por variables de entorno o headers.
Docs: https://code.claude.com/docs/en/mcp

**5.5 Precaución de seguridad**

Trata los servidores MCP como dependencias: instala solo de fuentes confiables. Un servidor malicioso puede intentar prompt injection.

### Práctica guiada
1. Instalar el MCP de GitHub, autenticarse con `/mcp` y pedir: *"Lista mis PRs abiertos y resume el más antiguo"*.
2. Instalar un MCP de base de datos (Postgres/SQLite de prueba) y pedir un análisis de datos en lenguaje natural.
3. Mover el servidor de scope local → project y revisar el `.mcp.json` generado.

### Tarea para alumnos
> **Entregable:** `.mcp.json` + transcript de un flujo completo.
1. Configura 2 servidores MCP relevantes para tu trabajo (uno remoto con OAuth y uno local stdio).
2. Diseña un flujo que combine ambos (ej.: "lee el issue #N de GitHub, verifica el dato en la base de datos, propón un fix").
3. Explica por escrito: ¿qué scope elegiste para cada servidor y por qué? ¿Qué riesgos de seguridad consideraste?

---

## Módulo 6 — Agentes: subagentes, agent teams y trabajo en paralelo

### Objetivos
- Crear subagentes personalizados con su propio contexto y herramientas.
- Saber cuándo usar subagente vs conversación principal vs agent team.
- Ejecutar sesiones paralelas con worktrees.

### Contenido

**6.1 Subagentes**

Un subagente es un asistente especializado con su propio system prompt, sus propias herramientas y su propia ventana de contexto. Sirve para aislar trabajo ruidoso (investigar, correr suites enormes de tests) sin llenar tu contexto principal.

Se crean con `/agents` (interfaz guiada) o como archivos Markdown:

`.claude/agents/code-reviewer.md`:
```markdown
---
name: code-reviewer
description: Revisor de código experto. Usar proactivamente después de escribir o modificar código.
tools: Read, Grep, Glob, Bash
model: sonnet
---

Eres un revisor senior. Revisa cambios recientes con `git diff`.
Prioriza: seguridad, manejo de errores, legibilidad y tests faltantes.
Reporta hallazgos por severidad (crítico / advertencia / sugerencia)
con archivo:línea y propuesta de fix.
```

- Claude delega automáticamente según el `description`, o puedes invocarlo explícito: *"Usa el subagente code-reviewer sobre mis cambios"*.
- Ubicaciones: `.claude/agents/` (proyecto) y `~/.claude/agents/` (usuario).
- Patrones: investigación en paralelo, encadenar subagentes, aislar operaciones de alto volumen.
Docs: https://code.claude.com/docs/en/sub-agents

**6.2 Agent teams**

Equipos de varios agentes coordinados por un líder, trabajando en paralelo sobre una tarea grande (ej.: revisión de código en paralelo, investigar hipótesis en competencia). Útil cuando las subtareas son independientes; vigila el consumo de tokens.
Docs: https://code.claude.com/docs/en/agent-teams

**6.3 Worktrees: sesiones paralelas sin conflictos**

Los git worktrees permiten correr varias sesiones de Claude sobre ramas distintas del mismo repo, cada una en su carpeta, sin pisarse:
```bash
git worktree add ../mi-app-feature-b feature-b
cd ../mi-app-feature-b && claude
```
Docs: https://code.claude.com/docs/en/worktrees

**6.4 ¿Cuál usar?**
- Tarea normal → conversación principal.
- Investigación/verificación aislada → subagente.
- Tarea grande y divisible en partes independientes → agent team o varias sesiones con worktrees.

### Práctica guiada
1. Crear el subagente `code-reviewer` y el subagente `test-runner` (corre tests y diagnostica fallos).
2. Encadenarlos: implementar una función → revisar con code-reviewer → validar con test-runner.
3. Demostración de dos sesiones paralelas con worktrees.

### Tarea para alumnos
> **Entregable:** los archivos de agentes + informe de 1 página.
1. Diseña 2 subagentes especializados para tu flujo (ej.: `security-auditor`, `db-query-validator`, `doc-writer`), con herramientas restringidas al mínimo necesario.
2. Ejecuta una tarea real que use ambos y compara: ¿qué mejoró frente a hacerlo todo en la conversación principal (contexto, calidad, tiempo)?
3. Pregunta extra: ¿por qué conviene restringir `tools` en un subagente?

---

## Módulo 7 — Plugins: empaquetar y distribuir todo lo anterior

### Objetivos
- Instalar plugins desde marketplaces.
- Crear un plugin propio que agrupe commands, skills, agentes, hooks y MCP.
- Publicar un marketplace para el equipo.

### Contenido

**7.1 Qué es un plugin**

Un plugin empaqueta en una sola unidad instalable: slash commands, skills, subagentes, hooks, servidores MCP e incluso LSP y temas. Es la forma correcta de distribuir tu configuración a un equipo o a la comunidad.

**7.2 Instalar plugins**

```bash
/plugin marketplace add usuario/repo-marketplace   # registrar un marketplace
/plugin                                            # explorar e instalar
/plugin install nombre-plugin@nombre-marketplace
```
Claude Code incluye acceso al marketplace oficial de Anthropic y al de la comunidad.
Docs: https://code.claude.com/docs/en/discover-plugins

**7.3 Estructura de un plugin**

```
mi-plugin/
├── .claude-plugin/
│   └── plugin.json        # manifiesto (nombre, descripción, versión)
├── commands/              # slash commands
├── agents/                # subagentes
├── skills/                # skills
├── hooks/
│   └── hooks.json         # hooks
└── .mcp.json              # servidores MCP
```

`plugin.json` mínimo:
```json
{
  "name": "mi-plugin",
  "description": "Herramientas del equipo backend",
  "version": "1.0.0"
}
```

Prueba local durante el desarrollo:
```bash
claude --plugin-dir ./mi-plugin
```

**7.4 Crear tu marketplace**

Un marketplace es un repo (típicamente GitHub) con `.claude-plugin/marketplace.json` que lista plugins y sus fuentes:
```json
{
  "name": "marketplace-equipo",
  "owner": { "name": "Tu Equipo" },
  "plugins": [
    { "name": "mi-plugin", "source": "./plugins/mi-plugin", "description": "Herramientas backend" }
  ]
}
```
El equipo lo agrega con `/plugin marketplace add tu-org/tu-repo`. Puedes incluso exigir marketplaces y plugins vía settings gestionados del equipo.
Docs: https://code.claude.com/docs/en/plugins y https://code.claude.com/docs/en/plugin-marketplaces

### Práctica guiada
1. Instalar un plugin del marketplace oficial y examinar qué componentes añadió.
2. Convertir lo construido en módulos 3–6 (commands + skill + agente + hook) en un plugin y probarlo con `--plugin-dir`.

### Tarea para alumnos
> **Entregable:** repo público (o privado compartido) con marketplace + plugin instalable.
1. Empaqueta tu configuración de los módulos anteriores como plugin versionado.
2. Publica un marketplace en GitHub y logra que un compañero lo instale con éxito.
3. Incluye un CHANGELOG y sube la versión (1.0.0 → 1.1.0) con una mejora tras el feedback del compañero.

---

## Módulo 8 — Automatización avanzada: headless, CI/CD y Agent SDK

### Objetivos
- Usar Claude Code en modo no interactivo dentro de scripts.
- Programar tareas y ejecutar Claude en CI (GitHub Actions).
- Conocer el Agent SDK para construir agentes propios.

### Contenido

**8.1 Modo headless (`claude -p`)**

```bash
# Uso básico
claude -p "explica qué hace este proyecto"

# Pipe de datos
cat error.log | claude -p "explica la causa raíz de este error"

# Salida estructurada para scripts
claude -p "cuenta los TODO del código" --output-format json

# Auto-aprobar herramientas específicas
claude -p "corre los tests y arregla los que fallen" --allowedTools "Bash,Edit,Read"
```
Esto convierte a Claude en una utilidad estilo Unix: puedes meterlo en builds, linters semánticos, generación de changelogs, etc.
Docs: https://code.claude.com/docs/en/headless

**8.2 Tareas programadas y loops**
Introducción rápida: `/loop`, recordatorios y routines. Se desarrolla a fondo en el **Módulo 10**.
Docs: https://code.claude.com/docs/en/scheduled-tasks

**8.3 GitHub Actions**

Con la Claude Code Action puedes mencionar `@claude` en issues y PRs para que implemente cambios, corrija bugs o responda dudas, y automatizar revisiones de código en cada PR.
Docs: https://code.claude.com/docs/en/github-actions

**8.4 Agent SDK (introducción)**

El mismo motor de Claude Code, como librería para construir tus propios agentes en TypeScript o Python:

```bash
npm install @anthropic-ai/claude-agent-sdk   # TypeScript
pip install claude-agent-sdk                  # Python
```

```python
import anyio
from claude_agent_sdk import query

async def main():
    async for message in query(prompt="Encuentra y corrige el bug en utils.py"):
        print(message)

anyio.run(main)
```
El SDK soporta sesiones, permisos, hooks, MCP, subagentes y salida estructurada — todo lo del curso, programable.
Docs: https://code.claude.com/docs/en/agent-sdk/overview

### Práctica guiada
1. Script bash que use `claude -p --output-format json` para auditar TODOs y generar un reporte.
2. Configurar la GitHub Action en un repo de prueba y abrir un issue con `@claude fix this`.

### Tarea final (proyecto integrador)
> **Entregable:** repo completo + demo de 5 minutos.
Construye un "asistente de equipo" que combine todo el curso:
1. CLAUDE.md y reglas del proyecto (M2).
2. Al menos 2 slash commands y 1 hook (M3).
3. 1 skill de dominio (M4).
4. 1 servidor MCP integrado (M5).
5. 1 subagente especializado (M6).
6. Todo empaquetado como plugin en un marketplace (M7).
7. Una automatización: script headless o pipeline CI (M8/M11).
8. *(Al completar los módulos 9–12, sumar:)* 1 hook de gobernanza (M9), 1 tarea programada (M10), el flujo GitLab completo issue → MR (M11) y el runbook de troubleshooting (M12).

**Rúbrica sugerida (100 pts):** funcionalidad de cada componente (10 pts × 7), calidad de la documentación (15), seguridad y manejo de permisos (10), demo (5).

---

## Módulo 9 — Hooks a fondo: automatización y gobernanza empresarial

### Objetivos
- Dominar todos los eventos del ciclo de vida y su semántica.
- Controlar a Claude con exit codes y salida JSON.
- Implementar hooks de compliance, auditoría y notificación de nivel empresarial.

### Contenido

**9.1 Eventos disponibles**

| Evento | Cuándo dispara | Uso típico |
|---|---|---|
| `PreToolUse` | Antes de ejecutar una herramienta | Bloquear/validar acciones |
| `PostToolUse` | Después de la herramienta | Formatear, lint, tests |
| `UserPromptSubmit` | Al enviar tu prompt | Inyectar contexto, filtrar secretos |
| `Stop` / `SubagentStop` | Cuando Claude termina un turno | Notificar, validar que no dejó trabajo a medias |
| `SessionStart` / `SessionEnd` | Inicio/fin de sesión | Cargar contexto, registrar métricas |
| `PreCompact` | Antes de compactar contexto | Respaldar el transcript |
| `Notification` | Cuando Claude pide atención | Enviar a Slack/Teams |

**9.2 El contrato: stdin JSON, exit codes y salida JSON**
- El hook recibe por stdin un JSON con el evento (herramienta, argumentos, rutas…).
- `exit 0` → todo bien; `exit 2` en PreToolUse → **bloquea** la acción y el stderr se le muestra a Claude como razón.
- También puedes responder con JSON (`{"decision": "block", "reason": "..."}`) para control fino.
Docs: https://code.claude.com/docs/en/hooks

**9.3 Soluciones empresariales (ejemplos reales)**

*a) Compliance — impedir fuga de secretos:* hook `PreToolUse` sobre `Edit|Write` que corre un escáner (ej. gitleaks) sobre el contenido; si detecta credenciales, `exit 2` con el motivo. Nadie —ni Claude— comitea un secreto.

*b) Auditoría — registrar cada comando Bash:*
```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Bash",
        "hooks": [
          { "type": "command", "command": "jq -r '\"\\(now|todate) \\(.tool_input.command)\"' >> /var/log/claude-audit.log" }
        ]
      }
    ]
  }
}
```
Con esto el equipo de seguridad tiene trazabilidad completa de lo que el agente ejecutó (puede enviarse a un SIEM en lugar de un archivo).

*c) Gobernanza — proteger rutas críticas:* bloquear ediciones a `infra/`, `.env*` o migraciones ya aplicadas, con mensaje que redirige a Claude al proceso correcto.

*d) Notificaciones — avisar al equipo:* hook `Stop` que publica en Slack/Teams un resumen cuando Claude termina una tarea larga en un servidor compartido.

*e) Calidad — gate automático:* hook `PostToolUse` que corre lint + tests del archivo tocado; si fallan, devuelve el error a Claude para que lo corrija de inmediato, sin intervención humana.

Distribución: estos hooks se versionan en `.claude/settings.json` del repo o se empaquetan en un **plugin** (Módulo 7) para toda la organización; en entornos gestionados pueden imponerse vía managed settings.

### Práctica guiada
1. Implementar el hook de auditoría de Bash y verlo registrar en vivo.
2. Implementar el bloqueo de `.env` con `exit 2` y observar cómo Claude explica que fue bloqueado y busca otra vía.

### Caso práctico (tarea)
> **Escenario empresarial:** eres el líder técnico de una fintech. Legal exige que ningún agente pueda: (1) editar la carpeta `payments/legacy/`, (2) ejecutar `git push --force`, (3) escribir credenciales en el código. Además, DevOps quiere log de todos los comandos.
> **Entregable:** `.claude/settings.json` con los 4 hooks + video/transcript demostrando cada bloqueo + 1 página explicando cómo lo desplegarías a 50 desarrolladores (pista: plugin + marketplace interno).

---

## Módulo 10 — Loop y tareas programadas

### Objetivos
- Programar trabajo recurrente y recordatorios desde Claude Code.
- Elegir correctamente entre `/loop`, tareas cloud, tareas de escritorio y cron del sistema.

### Contenido

**10.1 `/loop`: polling dentro de la sesión** (requiere v2.1.72+)

```
/loop 5m revisa si el deployment terminó y avísame qué pasó
/loop 20m /review-pr 1234        # también acepta skills/commands
```
Claude convierte el intervalo a una expresión cron, agenda el job y confirma cadencia e ID. Las tareas son **de sesión**: viven en la conversación actual y se detienen al iniciar una nueva; al reanudar con `--resume`/`--continue` regresan las no expiradas. El prompt agendado dispara **entre turnos**, nunca a mitad de una respuesta.

**10.2 Recordatorios one-shot en lenguaje natural**

"Recuérdame a las 4pm verificar el staging" → Claude fija la hora con cron, confirma cuándo disparará y la tarea se borra sola tras ejecutarse. Las horas se interpretan en tu zona horaria local.

**10.3 Las cuatro opciones y cuándo usar cada una**

| Opción | Dónde corre | ¿Sobrevive a cerrar sesión? | Caso de uso |
|---|---|---|---|
| `/loop` / cron in-session | Tu sesión CLI | No | Vigilar un deploy, babysit de un MR |
| Cloud tasks / Routines | Infraestructura de Anthropic | Sí, incluso con la laptop apagada | Reportes nocturnos, monitoreo 24/7 |
| Desktop tasks | Tu máquina (app Desktop; macOS/Windows) | Sí, mientras la máquina esté encendida | Tareas con tus archivos locales |
| cron del SO + `claude -p` | Tu servidor | Sí | Casos que nada más cubre |

Docs: https://code.claude.com/docs/en/scheduled-tasks

**10.4 Soluciones empresariales (ejemplos reales)**

*a) Vigilancia de despliegues:* `/loop 5m` que consulta el pipeline; al detectar fallo, analiza logs y propone el fix — el on-call recibe el diagnóstico ya hecho.

*b) Briefing diario del equipo:* tarea cloud a las 8am que revisa MRs estancados, tests que fallan de forma intermitente y issues nuevos, y publica el resumen donde el equipo lo lee.

*c) Monitoreo de errores:* cron del servidor cada hora: `claude -p "analiza los errores nuevos en logs/ y clasifícalos por severidad" --output-format json` alimentando un dashboard.

*d) Higiene de repositorio:* tarea semanal que detecta dependencias desactualizadas con CVEs y abre un MR con el upgrade propuesto.

⚠️ Gobernanza: en servidores compartidos o CI donde no quieres scheduling de fondo, se puede deshabilitar el scheduler por variable de entorno; y toda tarea desatendida debe correr con permisos mínimos (`--allowedTools` explícito).

### Práctica guiada
1. Crear un `/loop 2m` que vigile un build simulado y detenerlo cuando termine.
2. Crear un recordatorio one-shot en lenguaje natural y verificar que se autodestruye.

### Caso práctico (tarea)
> **Escenario empresarial:** tu empresa hace deploy a staging todos los días a las 6pm y el equipo pierde ~30 min diarios verificándolo manualmente.
> **Entregable:** (1) un `/loop` documentado para vigilancia en vivo durante la ventana de deploy, (2) una alternativa persistente (cloud/desktop task o cron + `claude -p`) para cuando nadie está conectado, y (3) una tabla justificando qué opción recomendarías a la empresa y su costo/beneficio.

---

## Módulo 11 — Flujos de trabajo profesionales con Git (GitLab)

### Objetivos
- Ejecutar el ciclo completo issue → rama → commits → Merge Request con Claude.
- Conectar Claude a GitLab vía MCP para trabajar con contexto real de issues y MRs.
- Integrar Claude Code en GitLab CI/CD (@claude en MRs) con seguridad empresarial.

### Contenido

**11.1 Git local con Claude**

Claude maneja git de forma nativa vía Bash: ramas, commits descriptivos, rebase, resolución de conflictos. Buenas prácticas:
- Pídele commits atómicos con formato convencional (refuérzalo con una skill del Módulo 4).
- `git push` genera la URL de creación del MR de GitLab — o usa `glab` (CLI oficial de GitLab) para crear el MR sin salir de la terminal:
```
"Crea la rama fix/sensor-timeout, commitea con formato convencional
y abre un MR con glab apuntando a develop, con descripción del cambio"
```

**11.2 GitLab MCP: trabajar con el contexto real**

Sin MCP, Claude solo ve tu código local y "adivina" el contexto del issue. Con el servidor MCP de GitLab, Claude lee el issue real, las discusiones de debugging y el historial de MRs similares antes de proponer el fix. Flujo profesional completo:
1. *"Lee el issue #42 de GitLab y resume el bug y las hipótesis discutidas"*
2. Plan mode → plan de fix aprobado por ti.
3. Implementación + tests.
4. Rama, commit y MR creado con descripción que referencia el issue (`Closes #42`).

**11.3 Claude Code en GitLab CI/CD (integración oficial, en beta)**

La integración usa GitLab CI/CD para correr tareas de IA en jobs aislados y devolver resultados vía MRs: GitLab escucha triggers (por ejemplo un comentario que menciona @claude en un issue, MR o hilo de review), el job junta el contexto del hilo y el repo, arma el prompt y ejecuta Claude Code. Cada interacción corre en un contenedor con reglas estrictas de red y filesystem, y todo cambio pasa por un MR para que las revisiones y aprobaciones sigan aplicando.

Job mínimo en `.gitlab-ci.yml` (adaptado del ejemplo oficial):
```yaml
stages:
  - ai

claude:
  stage: ai
  image: node:24-alpine3.21
  rules:
    - if: '$CI_PIPELINE_SOURCE == "web"'
    - if: '$CI_PIPELINE_SOURCE == "merge_request_event"'
  variables:
    GIT_STRATEGY: fetch
  before_script:
    - apk add --no-cache git curl bash
    - curl -fsSL https://claude.ai/install.sh | bash
  script:
    - >
      claude -p "${AI_FLOW_INPUT:-'Revisa este MR e implementa los cambios solicitados'}"
      --permission-mode acceptEdits
      --allowedTools "Read Edit Write mcp__gitlab"
```

**11.4 Seguridad empresarial en GitLab**
- Nunca comitees API keys: usa variables CI/CD **masked** (y protected) para `ANTHROPIC_API_KEY`.
- Para empresas: autenticación sin llaves estáticas vía **OIDC con Amazon Bedrock** o **Workload Identity Federation con Google Vertex AI** — Claude corre en tu nube, con endpoints regionales para latencia y soberanía de datos.
- Limita permisos del job y el egress de red; empieza con herramientas de solo lectura y agrega las mínimas necesarias.
- Revisa los MRs de Claude como los de cualquier contribuidor.
- Considera los costos: minutos de runner + tokens de API por interacción.
Docs: https://code.claude.com/docs/en/gitlab-ci-cd

**11.5 Soluciones empresariales (ejemplos reales)**

*a) Triage de issues:* @claude en un issue → Claude propone un MR completo con el fix y la explicación; el humano solo revisa y aprueba.

*b) Review complementario:* job en cada `merge_request_event` que revisa seguridad y estilo, publicando hallazgos como comentarios — se combina con las aprobaciones y security scanning nativos de GitLab, dejando rastro auditable.

*c) Self-hosted / regulados:* GitLab self-managed + Claude vía Bedrock con OIDC = el código nunca sale de tu infraestructura y no hay credenciales de larga vida en el CI.

### Práctica guiada
1. Ciclo completo local: issue → plan mode → fix → MR con `glab`.
2. Configurar el MCP de GitLab y repetir el flujo, ahora leyendo el issue real.
3. Demo del job de CI: agregar el `.gitlab-ci.yml`, la variable masked, y dispararlo manualmente desde CI/CD → Pipelines.

### Caso práctico (tarea)
> **Escenario empresarial:** una empresa con GitLab self-managed quiere que los bugs etiquetados `ai-fix` sean atendidos por Claude, con la regla de que ningún cambio llegue a `main` sin revisión humana y sin que existan API keys de larga vida en el CI.
> **Entregable:** repo GitLab con (1) el pipeline funcionando (vale con `ANTHROPIC_API_KEY` masked para la demo), (2) documento de arquitectura proponiendo la versión productiva con Bedrock/Vertex + OIDC, (3) evidencia del flujo completo: issue → @claude → MR → review humano → merge, y (4) análisis de riesgos (prompt injection desde issues públicos, costos de runner/tokens).

---

## Módulo 12 — Troubleshooting y diagnóstico

### Objetivos
- Diagnosticar problemas de instalación, configuración, hooks, MCP y skills.
- Construir un runbook de soporte interno para tu equipo.

### Contenido

**12.1 Herramientas de diagnóstico**

| Herramienta | Qué diagnostica |
|---|---|
| `claude doctor` | Salud de la instalación, versión, auto-updates |
| `claude --version` / `claude update` | Versión y actualización |
| `/status` | Estado de la sesión: cuenta, modelo, conectividad |
| `/context` | Qué está consumiendo la ventana de contexto |
| `/permissions` | Reglas allow/deny activas y de dónde vienen |
| `/hooks` | Hooks registrados y su origen |
| `/mcp` | Estado de servidores MCP y autenticación |
| `claude --debug` | Logs verbosos (incluye detalle de MCP) |

**12.2 Síntoma → diagnóstico (los 7 casos más comunes)**

1. **"Claude ignora mi CLAUDE.md"** → ¿lo iniciaste en la carpeta correcta? Verifica con `/memory` qué archivos cargó; revisa que no sea kilométrico (instrucciones diluidas).
2. **Mi skill nunca se activa** → el `description` no menciona los términos con que la invocas. Reescríbelo con qué hace + cuándo usarla; verifica ubicación (`.claude/skills/<n>/SKILL.md`) y frontmatter válido.
3. **Un hook no dispara** → `/hooks` para confirmar que está registrado; valida el JSON de settings; prueba el comando a mano con un stdin de ejemplo; recuerda que los cambios a settings requieren reiniciar la sesión o revisarse con `/hooks`.
4. **MCP no conecta** → `claude mcp list` (¿está registrado y en qué scope?), `/mcp` (¿falta OAuth?), `claude --debug` para ver el error real; en stdio, verifica que el comando corra solo en tu terminal.
5. **Permisos: pregunta demasiado / muy poco** → `/permissions` para ver reglas efectivas y su origen (user vs project vs local vs managed); recuerda la precedencia de settings.
6. **Contexto lleno / respuestas degradadas** → `/context` para ver al culpable (¿un MCP con demasiadas tools?), luego `/compact` o `/clear`, y mueve conocimiento estable a CLAUDE.md/skills.
7. **Instalación rota (PATH, Node, WSL)** → `claude doctor`; en cron/CI recuerda que el PATH es distinto: usa rutas absolutas al binario.

**12.3 Soluciones empresariales (ejemplos reales)**

*a) Runbook interno:* documento "primeros auxilios de Claude Code" con los 7 síntomas de arriba, distribuido como **skill** (`/troubleshoot-claude`)… el soporte se lo da el propio Claude.

*b) Hook de telemetría:* `SessionStart` que verifica versión mínima y configuración obligatoria de la empresa, avisando al dev si algo falta antes de empezar.

*c) Diagnóstico en CI:* paso previo del pipeline que corre `claude doctor` y `claude mcp list` y falla temprano con mensaje claro, en vez de dejar que el job de IA muera de forma críptica.

*d) Canal de escalamiento:* qué reportar (versión, `/status`, salida de `--debug`) y dónde (issues internos → soporte de Anthropic si aplica).

### Práctica guiada
1. Romper cosas a propósito: un hook con JSON inválido, una skill con description vago, un MCP con URL errónea — y diagnosticar cada una con las herramientas de 12.1.
2. Redactar en equipo el runbook de los 3 problemas que más les ocurrieron durante el curso.

### Caso práctico (tarea)
> **Escenario empresarial:** te contratan como "Claude Code champion" de una empresa de 30 devs. La primera semana llegan 3 tickets: (1) "a Juan no le carga el CLAUDE.md", (2) "el MCP de la base de datos no conecta en el equipo de datos", (3) "el hook de lint hace que Claude se quede en un bucle corrigiendo".
> **Entregable:** para cada ticket, el diagnóstico paso a paso (comandos usados y qué revelaron), la solución, y la medida preventiva. Bonus: empaqueta el runbook resultante como skill instalable vía tu plugin del Módulo 7.

---

## Anexo A — Chuleta de comandos

| Comando | Uso |
|---|---|
| `claude` / `claude "prompt"` | Iniciar sesión |
| `claude -c` / `claude -r` | Continuar / reanudar |
| `claude -p "..."` | Modo headless |
| `claude --add-dir <ruta>` | Acceso a carpetas extra |
| `claude mcp add/list/remove` | Gestionar MCP |
| `/init` `/memory` `/context` `/compact` `/clear` | Contexto y memoria |
| `/rewind` | Volver a un checkpoint |
| `/permissions` + `Shift+Tab` | Permisos y modos |
| `/agents` | Gestionar subagentes |
| `/mcp` | Estado y OAuth de MCP |
| `/plugin` | Marketplaces y plugins |
| `/hooks` | Ver hooks activos |
| `/model` `/usage` `/statusline` | Modelo, consumo, status |
| `/loop <intervalo> <prompt>` | Tarea recurrente en la sesión |
| `/tasks` | Panel de tareas programadas/paralelas |
| `/status` `claude doctor` `claude --debug` | Diagnóstico |

## Anexo B — Errores comunes de alumnos
1. Iniciar Claude en la carpeta equivocada (o en `~`) → contexto irrelevante.
2. CLAUDE.md kilométrico → instrucciones ignoradas; mejor corto + skills.
3. No dar forma de verificar (tests/build) → Claude "cree" que terminó.
4. Usar bypassPermissions fuera de un entorno aislado.
5. Descripciones de skills/agentes vagas → nunca se activan (o se activan siempre).
6. Instalar MCPs de fuentes no confiables.
7. No usar plan mode para cambios grandes.

## Anexo C — Recursos oficiales
- Documentación: https://code.claude.com/docs/en/overview
- Buenas prácticas: https://code.claude.com/docs/en/best-practices
- Referencia CLI: https://code.claude.com/docs/en/cli-reference
- Referencia de hooks: https://code.claude.com/docs/en/hooks
- Agent SDK: https://code.claude.com/docs/en/agent-sdk/overview
- Novedades semanales: https://code.claude.com/docs/en/whats-new/index
