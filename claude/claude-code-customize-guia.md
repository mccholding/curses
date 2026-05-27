# Guía del menú Customize en Claude Code

Esta guía explica cada opción del menú **Customize** de Claude Code, qué hace, cuándo usarla y un ejemplo práctico para cada una.

---

## 1. Output styles

**Qué es:** Cambia el "modo de respuesta" base de Claude. Modifica el system prompt principal sin perder las capacidades core (leer/escribir archivos, correr scripts, etc.).

Claude Code viene con tres estilos integrados:

- **Default** — el modo normal, optimizado para tareas de software engineering rápidas y concisas.
- **Explanatory** — agrega "Insights" educativos mientras te ayuda. Te explica por qué tomó cada decisión y qué patrones está siguiendo en tu codebase.
- **Learning** — modo colaborativo. Claude no solo te explica, también te pide que tú escribas piezas pequeñas de código (deja marcadores `TODO(human)` para que tú los implementes).

**Cuándo usarlo:**

- *Default* para trabajo del día a día.
- *Explanatory* cuando estás aprendiendo un codebase nuevo o stack nuevo.
- *Learning* cuando quieres aprender haciendo, no solo viendo a Claude trabajar.

**Cómo accederlo:** comando `/output-style` o desde `/config`.

**Ejemplo práctico:** Estás aprendiendo Rust. Activas `/output-style explanatory` y cada vez que Claude te genere código, te explica qué es un `Result<T, E>` y por qué uso `match` en vez de `if let`. Sin saturar tu sesión normal de trabajo.

También puedes crear estilos personalizados con `/output-style:new` (por ejemplo, "responde como senior architect", "respuestas en español", "siempre incluye tests").

---

## 2. Agents (Subagents)

**Qué es:** Asistentes especializados que Claude puede invocar para tareas específicas, cada uno con su propio system prompt, sus propias herramientas permitidas y hasta su propio modelo (Opus, Sonnet, Haiku).

Piensa en ellos como "miembros del equipo" especializados. El agent principal puede delegarle tareas a un subagent que tiene contexto aislado, lo que evita saturar tu conversación principal.

**Estructura típica:** archivos Markdown en `.claude/agents/` (proyecto) o `~/.claude/agents/` (personal):

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
3. Revisa secrets hardcoded, SQL injection
4. Reporta hallazgos con severidad y remediación
```

**Cuándo usarlo:**

- Tareas que necesitan contexto aislado (que no contaminen tu sesión principal).
- Trabajos que requieren un "especialista" con instrucciones distintas al main agent.
- Análisis paralelos (varios agents trabajando en módulos diferentes simultáneamente).

**Cómo accederlo:** comando `/agents` (interactivo).

**Ejemplo práctico:** Tienes un agent `db-migration-expert` que solo conoce las convenciones de migraciones de tu proyecto. Cuando le dices a Claude "necesito agregar una columna `last_login` a users", el main agent delega esa tarea al subagent, que la ejecuta sin saturar tu conversación principal con detalles internos.

---

## 3. Hooks

**Qué es:** Scripts o comandos que se ejecutan **automáticamente** en momentos específicos del ciclo de vida de Claude Code. A diferencia de las skills (que son sugerencias que Claude puede o no seguir), los hooks son **deterministas**: siempre se ejecutan.

**La diferencia clave:**

- `CLAUDE.md` y skills = reglas *advisory* (Claude las puede saltarse).
- Hooks = reglas *deterministas* (se ejecutan siempre, sin excepción).

**Eventos comunes donde se enganchan los hooks:**

- `PreToolUse` — antes de que Claude ejecute una herramienta. Puede bloquear, modificar o pedir confirmación.
- `PostToolUse` — después de que se usó una herramienta. Útil para logging o validación.
- `PermissionRequest` — cuando Claude va a pedir permiso al usuario.
- `Notification` — para reenviar eventos a Slack, email, etc.
- Eventos de sesión, compactación, cambios de configuración.

**Cuándo usarlos:**

- Cuando algo **debe ocurrir siempre**, sin depender del juicio del modelo.
- Formatear código automáticamente después de cada edit.
- Bloquear acceso a archivos sensibles (`.env`, secrets).
- Bloquear comandos peligrosos (`rm -rf /`).
- Correr el linter o tests después de cambios.
- Auditar cada comando bash para compliance.

**Cómo accederlos:** comando `/hooks` (interfaz interactiva).

**Ejemplo práctico:**

```yaml
PreToolUse:
  - matcher: "Read"
    hooks:
      - type: command
        command: "./scripts/protect-secrets.sh"
```

Si Claude intenta leer un `.env`, el hook intercepta y responde: "Access denied by hook: protect-secrets.sh prevented reading sensitive file."

**Tip:** Si una regla de tu equipo es crítica, no la pongas solo en `CLAUDE.md`. Conviértela en un hook.

---

## 4. Memory

**Qué es:** El sistema de memoria persistente de Claude Code. La pieza central es el archivo **`CLAUDE.md`**, donde guardas contexto del proyecto que Claude leerá automáticamente al iniciar cada sesión.

**Niveles de memoria:**

- **Project memory** — `./CLAUDE.md` en la raíz del repo. Se commitea con git, se comparte con el equipo.
- **User memory** — `~/.claude/CLAUDE.md`. Personal, válido para todos tus proyectos.
- **Local project** — `./CLAUDE.local.md`. Privado del proyecto pero no commiteado.

**Qué meter en `CLAUDE.md`:**

- Arquitectura del proyecto (monorepo, dónde vive cada cosa).
- Convenciones de código (TypeScript strict, no default exports, JSDoc obligatorio).
- Comandos comunes (`npm test`, `npm run db:migrate`).
- Patrones específicos (cómo crear endpoints, cómo organizar componentes).
- Decisiones arquitectónicas importantes.

**Tips importantes:**

- Respeta el límite de ~2,500 tokens. Si crece más, mueve detalle a skills.
- Usa `#` al inicio de un mensaje en chat para que Claude **agregue automáticamente** una nota a memoria sin generar respuesta.
- Commitea a git para que tu equipo lo comparta.
- Empieza simple, hazlo crecer cuando Claude cometa errores ("ah, no sabía que usábamos Prisma" → agrega esa info a CLAUDE.md).

**Cómo accederlo:** comando `/memory` (edita los archivos), o `/init` para generar un `CLAUDE.md` inicial automáticamente.

**Ejemplo práctico:**

```markdown
# Proyecto E-commerce

## Stack
- Next.js 14 con App Router
- Supabase (Postgres + Auth)
- Tailwind + shadcn/ui

## Reglas
- Server Components por defecto, "use client" solo si necesario
- Validación con Zod en TODOS los endpoints
- Nunca usar `any` en TypeScript

## Comandos
- `pnpm dev` — desarrollo local
- `pnpm test` — suite completa
- `pnpm db:push` — sincronizar schema con Supabase
```

---

## 5. Permissions

**Qué es:** Control granular sobre qué herramientas puede usar Claude y cuándo. Define el "blast radius" del agente: cuánto puede hacer sin pedirte permiso.

**Modos de permisos disponibles:**

- **default** — Claude pregunta antes de operaciones que modifican algo (escribir archivos, correr bash).
- **acceptEdits** — auto-aprueba ediciones de archivos. Otras herramientas (bash) siguen pidiendo permiso. Útil cuando confías en Claude y estás iterando rápido.
- **plan** — Claude solo puede analizar y crear planes, **no** modifica nada. Ideal para revisar antes de ejecutar.
- **bypassPermissions** — auto-aprueba **todo**. Solo en entornos controlados/aislados. Peligroso.

**Reglas declarativas (allow/deny):**

Puedes definir reglas finas en `.claude/settings.json` o `~/.claude/settings.json`:

```json
{
  "permissions": {
    "allow": ["Bash(npm test)", "Bash(npm run lint)"],
    "deny": ["Bash(rm -rf*)", "Read(.env*)"],
    "ask": ["Bash(git push*)"]
  }
}
```

**Orden de evaluación:** deny gana sobre ask, y ask gana sobre allow.

**Cuándo configurarlas:**

- Para entornos de equipo donde quieres garantizar que ciertos comandos no corran sin revisión.
- Para sandboxes/CI donde quieres autonomía total con bypass.
- Para auditorías de compliance (todo lo que toque DB requiere `ask`).

**Cómo accederlas:** comando `/permissions`.

**Ejemplo práctico:** En tu repo de producción, defines deny para `git push origin main` y `Bash(rm*)`. En un proyecto de prototipado, usas `acceptEdits` para que Claude itere sin interrumpirte.

---

## 6. MCP servers

**Qué es:** Configuración de las conexiones a servicios externos vía Model Context Protocol. Es donde gestionas qué MCP servers están conectados, su estado de autenticación, y agregas nuevos.

**Qué puedes hacer aquí:**

- Ver el estado de cada servidor MCP (conectado, desconectado, error de auth).
- Re-autenticar un servidor cuyo token expiró.
- Agregar nuevos servidores MCP manualmente.
- Configurar el `scope` (local del proyecto, usuario global, o managed por la org).
- Habilitar/deshabilitar servidores temporalmente.

**Diferencia con plugins:** Un plugin puede *bundlear* un MCP adentro (como pasa con GitHub, Supabase, Vercel). Pero también puedes tener MCP servers sueltos sin necesidad de un plugin.

**Cómo accederlo:** comando `/mcp`.

**Ejemplo práctico:** Tu MCP de Supabase muestra "auth failed". Vas a `/mcp`, ves el error, generas un nuevo token en supabase.com/dashboard, lo pegas y queda reconectado sin tener que reinstalar el plugin.

---

## 7. Manage plugins

**Qué es:** El gestor de plugins. Aquí instalas, deshabilitas, eliminas y descubres plugins de los marketplaces conectados.

**Pestañas típicas:**

- **Discover** — explorar plugins disponibles en los marketplaces conectados.
- **Installed** — los que ya tienes (con toggle on/off y botón de eliminar).
- **Marketplaces** — agregar/quitar fuentes de plugins (el oficial `claude-plugins-official` viene preconfigurado).
- **Errors** — diagnóstico de plugins que fallaron al cargar.

**Comandos útiles:**

- `/plugin install [nombre]@[marketplace]` — instalar.
- `/plugin marketplace add [URL o repo]` — agregar marketplace.
- `/plugin disable [nombre]` — deshabilitar sin desinstalar.

**Cuándo usarlo:**

- Instalar nuevos plugins para tu workflow.
- Limpiar plugins que no usas (cada plugin activo consume contexto).
- Cambiar de versión o source de un plugin.

**Cómo accederlo:** comando `/plugin`.

**Ejemplo práctico:** Trabajas en frontend con Figma. Vas a Discover, instalas el plugin oficial de Figma, te autenticas, y ahora Claude puede leer tus archivos de diseño y generar componentes directamente.

---

## 8. Open Claude in Terminal

**Qué es:** Atajo para abrir Claude Code en tu terminal del sistema (si estás usando una versión GUI o un IDE integrado).

Útil cuando tienes Claude Code embebido en VS Code o similar, y necesitas abrirlo en una terminal independiente para tareas más largas, debug, o ejecutar comandos manuales junto a Claude.

**Cuándo usarlo:**

- Sesiones largas o agentic loops que no quieres dentro del IDE.
- Cuando necesitas ver logs completos sin las limitaciones del panel del IDE.
- Para correr `claude` con flags específicos que el IDE no expone.

---

## Resumen rápido — cuándo usar cada uno

| Opción | Para qué | Determinismo |
|--------|----------|--------------|
| **Output styles** | Cambiar el "modo" de respuesta de Claude | Sugerencia |
| **Agents** | Especialistas con contexto aislado | Sugerencia |
| **Hooks** | Reglas que SIEMPRE deben ejecutarse | Determinista |
| **Memory** | Contexto persistente del proyecto | Sugerencia |
| **Permissions** | Qué puede hacer Claude sin pedir permiso | Determinista |
| **MCP servers** | Conexiones a servicios externos | N/A |
| **Manage plugins** | Instalar/desinstalar plugins | N/A |

## Una regla mental útil

- **¿Es contexto que Claude debe conocer?** → `Memory` (CLAUDE.md)
- **¿Es expertise para una tarea específica?** → `Skills` (no aparece en este menú pero relacionado)
- **¿Es una tarea aislada con su propio contexto?** → `Agents`
- **¿Debe ocurrir siempre, sin excepción?** → `Hooks`
- **¿Necesita acceder a un servicio externo?** → `MCP servers` (vía Plugins generalmente)
- **¿Es una restricción de seguridad?** → `Permissions`
- **¿Es un cambio de "personalidad"?** → `Output styles`
