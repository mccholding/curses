# Módulo 6 · Aplicaciones, acciones y rutinas programadas

**Duración:** 2 horas.

## Objetivos

- Distinguir consulta, creación y acción.
- Evaluar permisos antes de conectar una aplicación.
- Diseñar una rutina recurrente con criterio de relevancia.
- Establecer límites, condición de silencio y aprobación humana.

## Tipos de conexión

| Tipo | Ejemplo | Control mínimo |
|---|---|---|
| Lectura | consultar correo o archivos | alcance limitado |
| Creación | preparar documento o evento | revisión antes de compartir |
| Modificación | editar información existente | confirmación explícita |
| Comunicación | enviar o publicar | aprobación humana |
| Acción sensible | pagos, borrado, permisos | no automatizar sin controles fuertes |

## Diseño de una acción programada

```text
OBJETIVO
FUENTES AUTORIZADAS
FRECUENCIA
HORA Y ZONA HORARIA
CRITERIO DE RELEVANCIA
FORMATO
CONDICIÓN DE SILENCIO
CONDICIÓN DE PARADA
DESTINATARIO
APROBACIÓN NECESARIA
```

## Casos

- resumen diario de correos prioritarios;
- preparación de reuniones;
- seguimiento semanal de un proyecto;
- revisión mensual de documentos obsoletos;
- práctica educativa recurrente;
- monitoreo de un tema con notificación solo cuando exista un cambio material.

## Prueba adversarial

Simular:

- fuente sin acceso;
- información duplicada;
- zona horaria incorrecta;
- rutina sin novedades;
- dato sensible;
- acción que intenta comunicarse o modificar algo sin aprobación.

## Entregable

Una rutina documentada y probada, con matriz de permisos, condición de silencio y procedimiento de desactivación.
