# 05 · Construye una Empresa Potenciada por Agentes de IA

## De comprender agentes a construir un sistema empresarial real

Este curso es la especialización práctica del portafolio. Parte de `02 · Fundamentos de trabajar con IA` y lleva al alumno a diseñar, implementar, evaluar y operar un sistema agéntico con datos, herramientas, coordinación y control humano.

No vuelve a explicar qué es un agente, MCP, Skill, subagente, loop o tarea programada. Comienza construyendo.

## Propuesta de valor

```text
CURSO 02
Comprender las piezas y elegir el nivel correcto.
        ↓
CURSO 05
Construir, probar, desplegar y operar el sistema.
```

La arquitectura es neutral respecto al proveedor. **FerreAgente — El Tornillo de Oro** funciona como caso de referencia completo, pero cada participante trabaja sobre su empresa, organización o proyecto.

## Prerrequisito

- completar `02 · Fundamentos de trabajar con IA` o demostrar dominio equivalente;
- poder definir un proceso, una fuente de verdad y un criterio de éxito;
- tener un caso real o un proceso de práctica.

Una ruta de ChatGPT, Claude o Gemini es útil, pero no obligatoria. El Curso 01 solo se recomienda a quien necesite práctica adicional de Prompt, Context o Loop Engineering.

## Audiencia

- emprendedores y fundadores;
- dueños y operadores de PyME;
- consultores de automatización;
- analistas de operaciones;
- desarrolladores y perfiles técnicos;
- equipos de innovación;
- profesionales que necesitan construir un piloto verificable.

## Duración

- **10 semanas**;
- 11 módulos, incluido el mapa inicial;
- entre 3 y 5 horas semanales;
- un proyecto incremental durante todo el programa.

## Dos rutas de implementación

- **Low-code:** n8n o Make, hojas de cálculo, bases no-code y conectores.
- **Código:** Python, APIs, bases de datos, MCP y frameworks agénticos.

Ambas rutas deben cumplir los mismos contratos, pruebas, controles y criterios de operación.

## Núcleo que se conserva

1. selección y priorización del proceso;
2. contrato operativo del agente;
3. primer agente funcional;
4. datos, herramientas y permisos;
5. especialización de responsabilidades;
6. patrones de coordinación;
7. orquestador y rutinas;
8. evals, seguridad y aprobación humana;
9. producción, observabilidad e incidentes;
10. economía, costos y ROI;
11. integración final y manual operativo.

## Resultado final

Cada participante entrega un sistema mínimo con:

- un orquestador;
- tres agentes especializados;
- dos herramientas;
- una fuente de datos;
- un patrón de coordinación;
- cola de aprobación;
- evals reproducibles;
- observabilidad básica;
- cálculo de costos y retorno;
- manual operativo y de incidentes.

La arquitectura mínima puede reducirse cuando el proceso no justifique tres agentes. Se evalúa mejor una solución pequeña y confiable que una red compleja sin necesidad.

## Estructura

1. [Mapa del curso](./00-mapa-del-curso.md)
2. [Mapa agéntico de la empresa](./curso/00-mapa-agentico-empresa.md)
3. [Contrato operativo del agente](./curso/01-contrato-operativo-agente.md)
4. [Primer agente funcional](./curso/02-primer-agente-funcional.md)
5. [Datos, herramientas y MCP](./curso/03-datos-herramientas-mcp.md)
6. [Subagentes y especialización](./curso/04-subagentes-especializacion.md)
7. [Patrones de coordinación](./curso/05-patrones-coordinacion.md)
8. [Orquestador y rutinas](./curso/06-orquestador-operaciones.md)
9. [Evals, seguridad y control humano](./curso/07-evals-seguridad-control.md)
10. [Producción y operación](./curso/08-produccion-operacion.md)
11. [Economía y ROI](./curso/09-economia-roi.md)
12. [Integración final](./curso/10-integracion-final.md)
13. [Caso FerreAgente](./caso-referencia/ferreagente/README.md)
14. [Casos de adaptación](./casos-adaptacion/README.md)
15. [Rutas low-code y Python](./rutas/README.md)
16. [Plantillas](./plantillas/pack-plantillas.md)
17. [Evaluación y rúbrica](./material-instructor/evaluacion-y-rubrica.md)

## Regla de no repetición

Las definiciones introductorias ya cubiertas en el Curso 02 se utilizan como referencias de cinco minutos. El tiempo principal se dedica a:

- implementar;
- probar casos normales y adversariales;
- comparar alternativas simples;
- medir costos y calidad;
- documentar decisiones;
- operar y recuperar el sistema.

## Principio rector

Usar la solución más simple que funcione. Un workflow estructurado es preferible a un agente autónomo cuando el proceso es estable y predecible.
