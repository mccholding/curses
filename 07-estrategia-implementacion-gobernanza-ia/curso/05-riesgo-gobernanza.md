# Módulo 5 · Riesgo y gobernanza

## Pregunta directiva

¿Quién puede decidir, quién debe aprobar y quién responde cuando un sistema de IA falla?

## Marcos de referencia

El curso utiliza como referencias, no como certificación automática:

- NIST AI Risk Management Framework;
- NIST Generative AI Profile;
- ISO/IEC 42001;
- Principios de IA de la OCDE;
- regulación aplicable por jurisdicción y sector;
- políticas internas de seguridad, privacidad y cumplimiento.

NIST organiza el trabajo en funciones de gobierno, mapeo, medición y gestión. ISO/IEC 42001 aporta una lógica de sistema de gestión y mejora continua.

## Clasificación de riesgo

Evaluar:

- impacto sobre personas;
- sensibilidad de datos;
- efecto financiero;
- efecto legal o regulatorio;
- reversibilidad;
- posibilidad de detectar errores;
- escala y frecuencia;
- autonomía;
- exposición externa;
- dependencia de terceros.

## Niveles de control

| Nivel | Ejemplo | Control mínimo |
|---|---|---|
| Bajo | borradores internos | uso autorizado y revisión del usuario |
| Medio | análisis o recomendaciones | pruebas, fuentes y muestreo periódico |
| Alto | decisiones sobre clientes o empleados | evaluación formal, aprobación y monitoreo |
| Crítico | pagos, crédito, salud, seguridad o derechos | preparación asistida; ejecución humana y controles especializados |

La clasificación debe adaptarse a la regulación y al contexto real.

## Modelo de gobierno

Definir:

- patrocinador ejecutivo;
- dueño del proceso;
- dueño del sistema;
- datos y privacidad;
- seguridad;
- legal y cumplimiento;
- riesgo;
- talento y cambio;
- operación y soporte;
- auditoría o revisión independiente.

## Artefactos mínimos

- inventario de sistemas de IA;
- ficha de cada caso;
- clasificación de riesgo;
- evaluación de impacto cuando corresponda;
- registro de decisiones;
- matriz de responsabilidades;
- política de uso;
- procedimiento de incidentes;
- calendario de revisión;
- criterio de retiro.

## Taller

Simulación de comité ante un sistema que:

1. produjo una recomendación discriminatoria;
2. usó una fuente obsoleta;
3. ejecutó una acción no autorizada;
4. fue modificado por el proveedor sin aviso claro.

## Entregable

`modelo-gobierno-ia.md`

Debe incluir RACI, niveles de riesgo, puertas de aprobación, escalamiento y ciclo de revisión.

## Error frecuente

Crear un comité que aprueba documentos, pero no tiene inventario, métricas, capacidad de detener sistemas ni responsables operativos.
