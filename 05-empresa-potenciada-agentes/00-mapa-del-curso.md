# Mapa del curso 05

## Propósito

Construir un sistema agéntico empresarial que sea útil, verificable, operable y económicamente justificable.

El objetivo no es acumular agentes. El objetivo es diseñar una arquitectura mínima que resuelva procesos reales con límites claros.

## Proyecto transversal

Cada participante crea desde el primer día un repositorio neutral:

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
| 1 | ¿Qué contrato debe cumplir el agente? | ficha y prompt versionado |
| 2 | ¿Cómo ejecuta una acción real? | primer agente con herramientas |
| 3 | ¿Dónde vive la verdad del negocio? | datos, herramientas y permisos |
| 4 | ¿Cuándo dividir responsabilidades? | agente padre y especialistas |
| 5 | ¿Cómo se coordinan varios agentes? | flujo multiagente probado |
| 6 | ¿Cómo se reciben y enrutan objetivos? | orquestador y rutina programada |
| 7 | ¿Cómo sabemos que es confiable? | evals, guardrails y aprobaciones |
| 8 | ¿Cómo se opera después de la demo? | plan de producción e incidentes |
| 9 | ¿Vale la pena económicamente? | cálculo de ROI y decisión construir/comprar |
| 10 | ¿Puede otra persona entenderlo y operarlo? | demo, documentación y retrospectiva |

## Tres niveles de proyecto

### Nivel esencial

- Un agente.
- Una fuente de datos.
- Dos herramientas.
- Pruebas de aceptación.
- Escalamiento humano.

### Nivel profesional

- Tres agentes especializados.
- Un orquestador.
- Un patrón multiagente.
- Evals y observabilidad.
- Cola de aprobación.

### Nivel avanzado

- Cuatro o más agentes.
- Dos patrones de coordinación.
- MCP o conectores reutilizables.
- Tareas programadas.
- Despliegue y monitoreo.

## Arquetipos empresariales

El alumno puede trabajar sobre:

1. **Comercio y operaciones:** FerreAgente.
2. **Servicios profesionales:** consultora o agencia.
3. **Educación:** academia o centro de formación.
4. **Comercio electrónico:** tienda digital.
5. **Caso propio:** sujeto a aprobación por alcance y disponibilidad de datos.

## Decisiones que deben documentarse

En cada módulo el alumno registra en `docs/decisiones.md`:

- problema que intenta resolver;
- alternativa más simple considerada;
- nivel de autonomía elegido;
- datos y herramientas permitidos;
- riesgos;
- criterios de éxito;
- quién aprueba acciones sensibles;
- cómo se revierte un error.

## Política de alcance

No se considera un buen proyecto aquel que incluye muchos agentes sin necesidad. Se evaluará mejor una arquitectura pequeña y confiable que una red compleja sin pruebas.