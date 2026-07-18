# 05 · Construye una Empresa Potenciada por Agentes de IA

## Diseña, construye y opera un sistema de agentes para procesos reales

Este curso es la especialización práctica para pasar de utilizar asistentes de IA a construir sistemas que consultan datos, usan herramientas, coordinan especialistas, verifican resultados y trabajan bajo supervisión humana.

La arquitectura del curso es general. **FerreAgente — El Tornillo de Oro** funciona como caso de referencia completo, pero cada participante aplica los módulos a su propia empresa, organización o proyecto.

```text
PRINCIPIO GENERAL
        ↓
CASO FERREAGENTE
        ↓
TRANSFERENCIA A OTROS SECTORES
        ↓
CONSTRUCCIÓN DEL ALUMNO
        ↓
PRUEBA Y REFLEXIÓN
```

## Lugar en la ruta

Prerrequisitos recomendados:

1. [01 · Cómo comunicarnos y trabajar con la IA](../01-comunicarnos-trabajar-con-ia/README.md)
2. [02 · Fundamentos de trabajar con IA](../02-fundamentos-trabajar-con-ia/README.md)
3. [03 · Cómo usar Claude](../03-como-usar-claude/README.md), recomendado pero no obligatorio

El curso 01 aporta Prompt, Context y Loop Engineering. El curso 02 aporta el mapa tecnológico. El curso 03 enseña a implementar esos principios en Claude. Este curso integra las piezas en un sistema empresarial funcional.

## Audiencia

- Emprendedores y fundadores.
- Dueños y operadores de PyME.
- Consultores y profesionales de automatización.
- Analistas de operaciones.
- Desarrolladores y perfiles técnicos.
- Equipos de innovación que necesitan construir un piloto verificable.

## Duración

- **10 semanas.**
- **11 módulos**, incluido el módulo de preparación.
- Entre 3 y 5 horas semanales de clase, práctica y documentación.
- Un único proyecto incremental durante todo el programa.

## Dos rutas de implementación

- **Ruta low-code:** n8n o Make, hojas de cálculo, bases no-code y conectores.
- **Ruta con código:** Python, API de modelos, SQLite o PostgreSQL, MCP y frameworks agénticos.

Ambas rutas comparten arquitectura, políticas, pruebas, evaluaciones, controles humanos y estándares de calidad.

## Resultado final

Cada participante entrega un sistema mínimo con:

- un orquestador;
- tres agentes especializados;
- al menos dos herramientas;
- una fuente de datos;
- un patrón de coordinación;
- una cola de aprobación humana;
- evaluaciones reproducibles;
- observabilidad básica;
- cálculo de costos y retorno;
- manual operativo.

## Estructura

1. [Mapa del curso](./00-mapa-del-curso.md)
2. [Módulo 0 · Mapa agéntico de la empresa](./curso/00-mapa-agentico-empresa.md)
3. [Módulo 1 · Contrato operativo del agente](./curso/01-contrato-operativo-agente.md)
4. [Módulo 2 · Primer agente funcional](./curso/02-primer-agente-funcional.md)
5. [Módulo 3 · Datos, herramientas y MCP](./curso/03-datos-herramientas-mcp.md)
6. [Módulo 4 · Subagentes y especialización](./curso/04-subagentes-especializacion.md)
7. [Módulo 5 · Patrones de coordinación](./curso/05-patrones-coordinacion.md)
8. [Módulo 6 · Orquestador y rutinas](./curso/06-orquestador-operaciones.md)
9. [Módulo 7 · Evals, seguridad y control humano](./curso/07-evals-seguridad-control.md)
10. [Módulo 8 · Producción y operación](./curso/08-produccion-operacion.md)
11. [Módulo 9 · Economía y ROI](./curso/09-economia-roi.md)
12. [Módulo 10 · Integración final](./curso/10-integracion-final.md)
13. [Caso completo FerreAgente](./caso-referencia/ferreagente/README.md)
14. [Casos de adaptación](./casos-adaptacion/README.md)
15. [Rutas low-code y Python](./rutas/README.md)
16. [Pack de plantillas](./plantillas/pack-plantillas.md)
17. [Evaluación y rúbrica](./material-instructor/evaluacion-y-rubrica.md)

## Regla pedagógica

Cada módulo debe responder siete preguntas:

1. ¿Qué capacidad estamos diseñando?
2. ¿Cuándo conviene usarla y cuándo no?
3. ¿Cómo se implementa en FerreAgente?
4. ¿Cómo cambia en otros sectores?
5. ¿Qué agrega el alumno a su repositorio?
6. ¿Cómo demuestra que funciona?
7. ¿Qué no debe automatizar y por qué?

## Principio rector

Usar la solución más simple que funcione. Un workflow estructurado es preferible a un agente autónomo cuando el proceso es estable y predecible. La autonomía se añade únicamente donde la variabilidad lo justifica.