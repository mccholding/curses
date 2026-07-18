# Especialización · Codex

## Propósito

Usar Codex como agente técnico para comprender repositorios, modificar código, ejecutar comandos y pruebas, revisar cambios, automatizar flujos y entregar software con evidencia.

Codex no se enseña como autocompletado. Se enseña como un colaborador que necesita contexto, límites, herramientas, verificación y revisión humana.

**Fecha de corte del mapa:** 18 de julio de 2026.

## Audiencia

- desarrolladores;
- analistas técnicos;
- automatizadores;
- equipos de producto e ingeniería;
- personas con conocimientos básicos de terminal y Git.

## Prerrequisitos

- completar la Ruta profesional de ChatGPT o demostrar dominio equivalente;
- entender Prompt, Context y Loop Engineering;
- usar Git;
- leer código básico;
- ejecutar comandos en terminal;
- comprender pruebas y control de versiones.

## Duración sugerida

10 módulos de 2–3 horas más proyecto final.

## Mapa

| Módulo | Tema | Entregable |
|---:|---|---|
| 0 | Entorno, permisos y seguridad | repositorio de práctica y reglas |
| 1 | Contexto durable del repositorio | mapa de arquitectura y convenciones |
| 2 | Comprender una base de código | informe de flujos y dependencias |
| 3 | Planificar cambios | plan con archivos, riesgos y pruebas |
| 4 | Implementar y refactorizar | cambio pequeño con evidencia |
| 5 | Pruebas, debugging y verificación | suite o corrección reproducible |
| 6 | Git, GitHub y revisión | pull request revisable |
| 7 | Plugins, skills, MCP y herramientas | flujo técnico reutilizable |
| 8 | Automatizaciones y trabajo remoto | rutina repetible supervisada |
| 9 | Seguridad, evals y proyecto final | entrega técnica documentada |

## Principios

1. **Leer antes de editar.** Entender estructura, instrucciones y pruebas.
2. **Cambios pequeños.** Reducir superficie de error.
3. **Plan visible.** Declarar archivos, supuestos y validación.
4. **Pruebas como contrato.** No confiar en una explicación sin ejecución.
5. **Permiso mínimo.** Limitar carpetas, terminal, red y credenciales.
6. **No ocultar fallos.** Reportar pruebas no ejecutadas y limitaciones.
7. **Revisión humana.** El equipo conserva responsabilidad sobre merges y despliegues.

## Contenido por módulo

### Módulo 0 · Entorno y límites

- ChatGPT de escritorio y Codex;
- carpetas y repositorios locales;
- terminal;
- permisos;
- secretos;
- ramas de práctica;
- comandos permitidos y prohibidos.

### Módulo 1 · Contexto durable

- README y documentación;
- convenciones;
- comandos de instalación y pruebas;
- decisiones de arquitectura;
- definición de terminado;
- contexto que debe mantenerse actualizado.

### Módulo 2 · Comprensión de repositorios

- localizar puntos de entrada;
- trazar solicitudes y datos;
- mapear módulos;
- encontrar pruebas;
- identificar deuda y riesgos;
- explicar antes de modificar.

### Módulo 3 · Planificación

Un plan debe incluir:

```text
objetivo
archivos afectados
dependencias
supuestos
riesgos
migraciones
pruebas
rollback
criterios de aceptación
```

### Módulo 4 · Implementación

- cambios localizados;
- refactor sin alterar comportamiento;
- documentación;
- estilo del repositorio;
- manejo de errores;
- revisión del diff.

### Módulo 5 · Pruebas y debugging

- reproducir antes de corregir;
- prueba que falla;
- hipótesis;
- cambio mínimo;
- regresión;
- pruebas unitarias, integración y flujo;
- evidencia de ejecución.

### Módulo 6 · GitHub y revisión

- issues;
- ramas;
- commits;
- pull requests;
- revisión de diffs;
- comentarios;
- CI;
- preparación para revisión humana.

### Módulo 7 · Plugins, skills, MCP y herramientas

- guardar flujos repetibles;
- conectar servicios autorizados;
- crear comandos o herramientas componibles;
- documentar entradas, salidas y errores;
- aislar acciones destructivas;
- probar permisos.

### Módulo 8 · Automatizaciones

- triage de errores;
- actualización de documentación;
- revisión periódica de dependencias;
- preparación de reportes;
- tareas remotas;
- objetivos durables;
- condiciones de parada y notificación.

### Módulo 9 · Seguridad y proyecto final

- análisis en repositorios autorizados;
- protección de secretos;
- revisión de dependencias;
- no ejecutar código no confiable sin aislamiento;
- evidencia de pruebas;
- manual de operación;
- revisión humana antes de merge o despliegue.

## Proyecto final

Completar una mejora real en un repositorio con:

- issue o brief;
- mapa del repositorio;
- plan aprobado;
- implementación;
- pruebas;
- revisión del diff;
- documentación;
- pull request;
- análisis de riesgos;
- retrospectiva.

## Evaluación

| Componente | Peso |
|---|---:|
| Comprensión y planificación | 20 % |
| Calidad del cambio | 25 % |
| Pruebas y verificación | 25 % |
| Git y documentación | 15 % |
| Seguridad y límites | 15 % |

## Desarrollo pendiente

Este archivo define la especialización. Para impartirla se debe construir un repositorio de práctica con errores deliberados, issues, pruebas, CI y soluciones de referencia. No se debe practicar por primera vez sobre un sistema crítico.