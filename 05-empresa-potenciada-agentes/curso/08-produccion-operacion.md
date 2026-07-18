# Módulo 8 · Producción y operación

**Duración:** 5 horas.

## Objetivos

- Pasar de una demostración a un sistema operable.
- Diseñar observabilidad, límites y recuperación.
- Administrar secretos, versiones y despliegues.
- Crear un manual de incidentes.

## Diferencia entre demo y producción

Una demo prueba que algo puede funcionar. Producción exige que el sistema:

- sea reproducible;
- tenga permisos controlados;
- registre decisiones;
- sobreviva a errores;
- limite costos;
- pueda actualizarse y revertirse;
- tenga un responsable.

## Controles operativos

### Configuración y secretos

- variables de entorno;
- almacén de secretos;
- separación entre desarrollo y producción;
- rotación de claves;
- permisos mínimos.

### Observabilidad

Registrar:

- identificador de ejecución;
- usuario u origen;
- modelo y versión;
- prompt o configuración versionada;
- herramientas llamadas;
- entradas y salidas permitidas;
- costos y latencia;
- errores;
- aprobaciones.

### Límites

- máximo de pasos;
- máximo de reintentos;
- timeout;
- presupuesto por ejecución;
- presupuesto diario;
- tamaño de contexto;
- concurrencia.

### Recuperación

- reintento seguro;
- idempotencia;
- cola de errores;
- fallback;
- rollback;
- modo manual;
- pausa de emergencia.

## Versionamiento

Versionar:

- prompts;
- herramientas;
- esquemas;
- modelos;
- evaluaciones;
- fuentes de datos;
- decisiones de arquitectura.

Todo cambio debe pasar la suite de evals antes del despliegue.

## FerreAgente

El caso de referencia documenta:

- ambientes de prueba y operación;
- presupuesto diario;
- logs del briefing;
- cola de órdenes pendientes;
- procedimiento cuando inventario o finanzas no responde;
- proceso para desactivar una rutina.

## Construcción

```text
observabilidad/esquema-logs.md
observabilidad/dashboard.md
docs/despliegue.md
docs/runbook-incidentes.md
docs/versiones.md
configuracion/limites.md
```

## Simulacros

1. API no disponible;
2. respuesta lenta;
3. costo superior al presupuesto;
4. ejecución duplicada;
5. cambio de prompt que rompe una política;
6. dato sensible en un log;
7. necesidad de volver a la versión anterior.

## Entregable

Plan de producción, runbook de incidentes y demostración de un rollback o fallback controlado.