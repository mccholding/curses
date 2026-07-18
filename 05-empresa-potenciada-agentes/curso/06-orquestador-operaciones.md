# Módulo 6 · Orquestador y rutinas operativas

**Duración:** 5 horas.

## Objetivos

- Diseñar un orquestador empresarial.
- Clasificar solicitudes por dominio, complejidad y riesgo.
- Descomponer objetivos y controlar dependencias.
- Crear rutinas programadas con trazabilidad.

## Componentes del orquestador

```text
clasificador
→ descompositor
→ enrutador
→ controlador de ejecución
→ agregador
→ verificador
→ entrega o escalamiento
```

### Clasificador

Determina:

- dominio;
- intención;
- urgencia;
- complejidad;
- nivel de riesgo;
- necesidad de aprobación.

### Descompositor

Crea subtareas únicamente cuando sea necesario. Declara dependencias y condiciones de finalización.

### Enrutador

Selecciona trabajadores según capacidades, permisos, costo y disponibilidad.

### Agregador

Combina resultados sin ocultar contradicciones ni inventar una conclusión.

## FerreAgente

El Orquestador de Operaciones coordina Ventas, Inventario, Compras, Finanzas y Marketing.

Prueba multiárea:

> Las ventas de taladros bajaron. Investiga la causa y propón una acción que no comprometa el margen ni el inventario.

Rutinas:

- briefing matutino;
- propuesta semanal de compras;
- cierre mensual;
- seguimiento de cobros vencidos.

## Rutinas programadas

Toda rutina debe definir:

- horario y zona horaria;
- fuentes consultadas;
- fecha de corte;
- pasos;
- verificación;
- presupuesto de tiempo o tokens;
- condición de no ejecución;
- canal de entrega;
- responsable humano.

Una tarea programada no debe ejecutar acciones sensibles sin aprobación solo porque corre automáticamente.

## Transferencia

- Consultora: briefing de proyectos y riesgos.
- Academia: alertas de estudiantes que necesitan apoyo.
- Ecommerce: reporte de pedidos, devoluciones y quiebres.
- Marketing: análisis semanal y propuesta de experimentos.

## Construcción

```text
orquestador/orquestador.*
orquestador/capacidades-agentes.md
orquestador/rutinas.md
observabilidad/estado-ejecucion.*
aprobaciones/pendientes.*
```

## Pruebas

1. solicitud de un dominio;
2. solicitud multiárea;
3. objetivo ambiguo;
4. objetivo de alto riesgo;
5. trabajador no disponible;
6. resultados contradictorios;
7. rutina sin datos nuevos;
8. rutina que supera presupuesto.

## Entregable

Orquestador que enruta al menos tres tipos de solicitud y una rutina programada que genera un informe verificable sin ejecutar acciones sensibles.