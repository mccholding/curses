# Mapa del curso 05

## Propósito

Construir un sistema agéntico empresarial útil, verificable, operable y económicamente justificable.

## Punto de partida

El alumno ya completó `02 · Fundamentos de trabajar con IA` o domina sus conceptos.

Por eso el curso no comienza preguntando “¿qué es un agente?”. Comienza preguntando:

> ¿Qué proceso merece IA y cuál es la arquitectura mínima que puede resolverlo con seguridad?

## Proyecto transversal

Cada participante crea un repositorio neutral:

```text
empresa-potenciada-por-agentes/
├── configuracion/
├── prompts/
├── datos/
├── agentes/
├── herramientas/
├── orquestador/
├── evals/
├── aprobaciones/
├── observabilidad/
└── docs/
```

FerreAgente utiliza la misma arquitectura dentro de `caso-referencia/ferreagente/`.

## Progresión

| Módulo | Pregunta central | Entregable principal |
|---:|---|---|
| 0 | ¿Qué proceso merece IA? | mapa agéntico y priorización |
| 1 | ¿Qué contrato debe cumplir? | contrato operativo versionado |
| 2 | ¿Cómo ejecuta una acción real? | primer agente funcional |
| 3 | ¿Dónde vive la verdad y qué puede usar? | datos, herramientas y permisos |
| 4 | ¿Cuándo dividir responsabilidades? | especialistas probados |
| 5 | ¿Cómo coordinar sin crear complejidad innecesaria? | patrón comparado contra workflow simple |
| 6 | ¿Cómo enrutar objetivos y rutinas? | orquestador funcional |
| 7 | ¿Cómo demostrar confiabilidad? | evals, guardrails y aprobaciones |
| 8 | ¿Cómo operar después de la demo? | observabilidad, incidentes y producción |
| 9 | ¿Vale la pena? | costo, ROI y decisión construir/comprar |
| 10 | ¿Puede otra persona operarlo? | demo, documentación y retrospectiva |

## Tres niveles de proyecto

### Esencial

- un agente;
- una fuente de datos;
- dos herramientas;
- pruebas de aceptación;
- escalamiento humano.

### Profesional

- hasta tres agentes especializados;
- orquestador;
- patrón de coordinación;
- evals y observabilidad;
- cola de aprobación.

### Avanzado

- cuatro o más agentes solo cuando estén justificados;
- dos patrones de coordinación;
- MCP o conectores reutilizables;
- tareas programadas;
- despliegue y monitoreo.

## Regla de no repetición

No dedicar módulos completos a definir agentes, subagentes, MCP, Skills, loops o tareas programadas.

Cada concepto se recuerda mediante una referencia breve y se aplica inmediatamente en:

- arquitectura;
- implementación;
- pruebas;
- seguridad;
- costos;
- operación.

## Decisiones obligatorias

En cada módulo el alumno registra:

- problema que intenta resolver;
- alternativa más simple;
- autonomía elegida;
- datos y herramientas permitidos;
- riesgos;
- criterios de éxito;
- aprobaciones humanas;
- mecanismo de reversión.

## Política de alcance

Una arquitectura pequeña, entendible y probada recibe mejor evaluación que una red compleja de agentes sin necesidad, evidencia ni capacidad de recuperación.
