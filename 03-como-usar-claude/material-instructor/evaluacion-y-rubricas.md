# Evaluación y rúbricas

## Principios

La evaluación debe medir si el alumno puede producir un resultado confiable, no si recuerda dónde está cada botón.

Se evalúan cinco capacidades:

1. Elegir la herramienta correcta.
2. Preparar contexto y fuentes.
3. Producir un entregable útil.
4. Verificar y controlar riesgos.
5. Documentar un flujo que otra persona pueda repetir.

---

# Ruta profesional

## Evidencias por módulo

| Módulo | Evidencia |
|---:|---|
| 0 | Mapa personal de casos de uso |
| 1 | Análisis verificable de un archivo |
| 2 | Artifact funcional con criterios de aceptación |
| 3 | Project con instrucciones y fuentes organizadas |
| 4 | Informe trazable con tabla de evidencia |
| 5 | Flujo conectado y matriz de permisos |
| 6 | Ficha de delegación y plan de automatización gradual |
| 7 | Proyecto final y demostración |

## Rúbrica del proyecto final profesional

| Criterio | Excelente | Aceptable | Insuficiente | Peso |
|---|---|---|---|---:|
| Problema y alcance | Problema real, medido y con límites claros | Problema real pero alcance amplio | Problema hipotético o ambiguo | 15% |
| Elección de superficie | Usa la combinación mínima y la justifica | Funciona, aunque incluye herramientas innecesarias | La herramienta no corresponde al problema | 10% |
| Contexto y fuentes | Fuentes clasificadas, actuales y mantenibles | Fuentes útiles pero poco organizadas | Fuentes incompletas, mezcladas u obsoletas | 15% |
| Instrucciones | Claras, verificables y reutilizables | Suficientes para ejecutar | Vagas o dependientes de interpretación | 10% |
| Entregable | Resuelve la necesidad y cumple criterios | Es útil con ajustes menores | No es utilizable sin rehacerlo | 15% |
| Verificación | Evidencia, fuente de verdad y manejo de incertidumbre | Revisión básica | Confianza ciega o verificación subjetiva | 15% |
| Seguridad | Permisos mínimos y checkpoints claros | Controles generales | Acciones críticas sin aprobación | 10% |
| Medición y mantenimiento | Tiene línea base, métrica y responsable | Tiene una métrica aproximada | No mide ni define mantenimiento | 10% |

## Condiciones de no aprobación

Un proyecto no aprueba si:

- expone información restringida sin justificación;
- automatiza envío, publicación, borrado o pago sin checkpoint;
- presenta datos inventados como hechos;
- no define cómo se verifica el resultado;
- no puede ser explicado o repetido por otra persona.

---

# Especialización Claude Code

## Evidencias acumulativas

| Módulo | Evidencia técnica |
|---:|---|
| 1 | Instalación, diagnóstico y primer cambio |
| 2 | CLAUDE.md, permisos y refactor verificado |
| 3 | Comandos y hooks iniciales |
| 4 | Skill con pruebas de activación |
| 5 | Flujo MCP con scopes justificados |
| 6 | Subagentes y comparación de resultados |
| 7 | Plugin y marketplace instalable |
| 8 | Automatización headless o CI |
| 9 | Hooks de compliance y auditoría |
| 10 | Tarea programada con límites |
| 11 | Flujo issue → cambio → MR → revisión |
| 12 | Runbook de troubleshooting |

## Rúbrica del proyecto integrador técnico

| Criterio | Peso |
|---|---:|
| Funcionalidad del flujo completo | 20% |
| CLAUDE.md, reglas y permisos | 10% |
| Skill y subagente | 15% |
| MCP y manejo de credenciales | 10% |
| Hooks y gobernanza | 15% |
| Plugin y capacidad de instalación | 10% |
| Automatización o CI/CD | 10% |
| Documentación, demo y troubleshooting | 10% |

## Pruebas mínimas de aceptación

El proyecto técnico debe demostrar:

1. Instalación limpia en otro entorno o por otro alumno.
2. Una tarea que termina con tests o verificación objetiva.
3. Un intento bloqueado por permisos o hook.
4. Una integración MCP con permisos mínimos.
5. Una ejecución repetible mediante comando, Skill o pipeline.
6. Recuperación documentada de al menos un fallo.

## Retroalimentación recomendada

Usar el formato:

```text
FORTALEZA
Qué funcionó y por qué.

RIESGO
Qué podría fallar en un entorno real.

SIGUIENTE CAMBIO
La mejora concreta de mayor impacto.

EVIDENCIA
Archivo, comando, captura o prueba que demuestra el resultado.
```
