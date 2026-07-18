# 03 · Cómo usar Claude: de cero a avanzado

Curso organizado como una ruta progresiva para aprender el ecosistema Claude sin mezclar públicos ni niveles técnicos.

## Lugar en la ruta

Este es el **tercer curso** de la ruta recomendada:

1. [**01 · Cómo comunicarnos y trabajar con la IA**](../01-comunicarnos-trabajar-con-ia/README.md)
2. [**02 · Fundamentos de trabajar con IA**](../02-fundamentos-trabajar-con-ia/README.md)
3. **03 · Cómo usar Claude: de cero a avanzado**

El curso 01 enseña Prompt Engineering, Context Engineering y Loop Engineering. El curso 02 explica el mapa general de tecnologías y niveles de autonomía. Este curso 03 se concentra en **implementar esos principios dentro de Claude como plataforma de trabajo**.

## Decisión estructural

El curso anterior intentaba cubrir Chat, Projects, Claude Code, agentes, Skills, MCP y conectores en 8–10 horas. Eso mezclaba dos audiencias con necesidades distintas.

La nueva versión se divide en dos rutas:

### Ruta A · Claude para profesionales

Para personas de operaciones, administración, educación, marketing, consultoría, liderazgo, análisis y creación de contenido.

- **Duración sugerida:** 16 horas.
- **Formato:** 8 módulos progresivos con práctica y entregables.
- **Prerrequisito:** comprender cómo diseñar instrucciones, contexto, fuentes, verificación y ciclos de trabajo sencillos.
- **Resultado:** diseñar un espacio de trabajo completo en Claude, con Projects, archivos, Artifacts, investigación, conectores, delegación y controles humanos.

[Ver la Ruta profesional](./ruta-profesional/README.md)

### Ruta B · Especialización Claude Code

Para desarrolladores y perfiles técnicos con conocimientos básicos de terminal y Git.

- **Duración sugerida:** 12 módulos de 2–3 horas más tareas.
- **Prerrequisito:** completar la Ruta A o demostrar dominio equivalente de Claude.
- **Resultado:** personalizar Claude Code con CLAUDE.md, reglas, Skills, MCP, subagentes, hooks, plugins, CI/CD y automatización.

[Ver la Especialización Claude Code](./especializacion-claude-code/README.md)

## Relación con las tres ingenierías

| Curso 01 | Aplicación en Claude |
|---|---|
| Prompt Engineering | instrucciones, prompts y criterios de aceptación |
| Context Engineering | Projects, archivos, conocimiento, conversaciones y CLAUDE.md |
| Loop Engineering | delegación, tareas, agentes, hooks, verificación y automatización |

## Estructura del repositorio

```text
03-como-usar-claude/
├── README.md
├── 00-mapa-del-curso.md
├── ruta-profesional/
│   ├── README.md
│   ├── 01-ecosistema-chat-y-archivos.md
│   ├── 02-artifacts-proyectos-y-conocimiento.md
│   ├── 03-conectores-delegacion-y-automatizacion.md
│   └── 04-equipos-gobernanza-y-proyecto-final.md
├── especializacion-claude-code/
│   ├── README.md
│   └── curso-claude-code.md
└── material-instructor/
    ├── plan-de-ampliacion.md
    └── evaluacion-y-rubricas.md
```

## Principio pedagógico

Cada módulo debe incluir:

1. objetivos observables;
2. una demostración corta;
3. una práctica guiada;
4. un caso real por audiencia;
5. un entregable verificable;
6. una evaluación o reflexión de cierre.

## Qué se conserva del curso anterior

El material anterior sigue siendo útil como banco de explicaciones, ejemplos y prompts. Sin embargo, deja de ser el documento principal. Se mantiene en la carpeta `claude/` como material legado mientras se migra y depura.