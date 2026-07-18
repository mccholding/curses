# Plan de ampliación del curso

## Diagnóstico del curso anterior

El contenido anterior tenía buenas explicaciones y muchos ejemplos, pero presentaba cuatro problemas estructurales:

1. **Alcance excesivo para 8–10 horas.** Chat, Projects, Claude Code, agentes, Skills y MCP no caben con profundidad en ese tiempo.
2. **Audiencias mezcladas.** Una persona de operaciones no necesita el mismo recorrido que un desarrollador.
3. **Solapamiento con Prompting y Fundamentos.** Varias secciones repetían habilidades ya cubiertas en los cursos 01 y 02.
4. **Poca separación entre conocer una función y dominar un flujo.** Faltaban más entregables, criterios de calidad y evaluación acumulativa.

## Nueva arquitectura

### Curso principal

**Claude para profesionales**, 8 módulos y 16 horas.

Su promesa debe ser:

> Diseña un sistema de trabajo confiable en Claude para analizar información, producir entregables, organizar conocimiento, conectar herramientas y delegar tareas con control humano.

### Especialización

**Claude Code**, 12 módulos y 24–36 horas.

Su promesa debe ser:

> Configura, extiende y automatiza Claude Code para trabajar de forma segura sobre repositorios y flujos de entrega profesionales.

## Qué migrar del documento legado

| Material anterior | Destino recomendado |
|---|---|
| Explicación del ecosistema y modelos | Ruta profesional, módulo 0 |
| Ejemplos de Chat y archivos | Ruta profesional, módulo 1 |
| Artifacts | Ruta profesional, módulo 2 |
| Projects e instrucciones | Ruta profesional, módulo 3 |
| Investigación y verificación | Ruta profesional, módulo 4 |
| Conectores y MCP no técnico | Ruta profesional, módulo 5 |
| Agentes por rol y flujos combinados | Ruta profesional, módulo 6 |
| Seguridad, equipos y casos reales | Ruta profesional, módulo 7 |
| Claude Code básico | Eliminar del curso principal y remitir a la especialización |
| CLAUDE.md, permisos, hooks y Skills | Especialización Claude Code |

## Ampliaciones prioritarias para la Ruta profesional

### 1. Guía visual actualizada de cada superficie

Crear capturas o videos cortos para:

- Chat;
- Projects;
- Artifacts;
- conectores;
- trabajo agéntico o tareas;
- transición a Claude Code.

Las interfaces cambian con frecuencia. Las capturas deben llevar fecha de actualización.

### 2. Banco de archivos de práctica

Preparar un paquete descargable con:

- reporte PDF;
- CSV con errores deliberados;
- brandbook;
- política interna con versiones contradictorias;
- transcripción de reunión;
- carpeta de proyecto con documentos útiles y ruido.

### 3. Casos por audiencia

Construir un caso transversal para cada perfil:

- PyME;
- corporativo;
- servicios profesionales;
- educación;
- marketing;
- liderazgo.

Cada caso debe recorrer Chat → Artifact → Project → conector → delegación.

### 4. Laboratorio de errores

Diseñar prácticas donde Claude:

- inventa una fuente;
- mezcla clientes;
- usa un documento obsoleto;
- interpreta una cifra de forma incorrecta;
- propone una acción sin aprobación;
- responde con un entregable que no cumple el formato.

El alumno debe detectar, explicar y corregir el fallo.

### 5. Guía de adopción empresarial

Agregar plantillas para:

- selección de procesos;
- clasificación de datos;
- matriz de permisos;
- checklist de revisión humana;
- medición antes/después;
- registro de incidentes;
- responsable de mantenimiento de Projects.

## Ampliaciones prioritarias para Claude Code

### 1. Repositorio de laboratorio

Crear un repo intencionalmente pequeño que incluya:

- una aplicación funcional;
- tests;
- errores controlados;
- carpeta legacy protegida;
- `.env.example`;
- issues para resolver;
- pipeline de CI básico.

### 2. Soluciones de referencia

Para cada tarea, mantener:

- versión inicial;
- solución mínima;
- solución avanzada;
- errores comunes;
- criterios de evaluación.

### 3. Plantillas reutilizables

Crear ejemplos listos para copiar de:

- CLAUDE.md;
- `.claude/settings.json`;
- `.claude/rules/`;
- Skills;
- subagentes;
- hooks;
- plugin y marketplace;
- GitHub Actions y GitLab CI.

### 4. Proyecto por etapas

En vez de esperar al final, el proyecto integrador debe crecer:

```text
M2  → CLAUDE.md y permisos
M3  → comandos y hooks
M4  → Skill
M5  → MCP
M6  → subagente
M7  → plugin
M8  → automatización
M9  → gobernanza
M10 → tarea programada
M11 → flujo Git
M12 → runbook
```

## Control de vigencia técnica

Claude y Claude Code cambian rápidamente. Antes de cada cohorte, revisar contra documentación oficial:

- métodos de instalación;
- nombres de comandos y flags;
- modos de permisos;
- estructura de Skills, agentes y plugins;
- eventos de hooks;
- transportes y scopes de MCP;
- tareas programadas;
- integraciones de GitHub y GitLab;
- disponibilidad por plan o sistema operativo.

Marcar cada material con:

```text
Última validación técnica: AAAA-MM-DD
Versión de Claude Code probada: X.Y.Z
Sistema operativo de prueba: macOS / Windows / Linux
```

## Siguiente iteración recomendada

1. Revisar el documento legado y migrar únicamente los mejores ejemplos.
2. Crear materiales descargables para los módulos 1–4.
3. Construir el repositorio de laboratorio de Claude Code.
4. Probar ambos cursos con un grupo pequeño.
5. Medir dónde los alumnos se atascan y ajustar duración.
