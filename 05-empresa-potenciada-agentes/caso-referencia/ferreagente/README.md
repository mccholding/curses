# Caso de referencia · FerreAgente

## El Tornillo de Oro

FerreAgente es la implementación oficial utilizada por el instructor para demostrar el curso de principio a fin.

No es la identidad del curso ni un proyecto obligatorio para todos los alumnos. Su función es mantener un ejemplo coherente que permita ver cómo las decisiones se acumulan entre módulos.

## Negocio

Ferretería operada por una persona con procesos de:

1. ventas y atención;
2. inventario;
3. compras;
4. finanzas;
5. operaciones;
6. marketing.

## Arquitectura de referencia

```text
ferreagente/
├── configuracion/
├── prompts/
├── datos/
├── agentes/
│   ├── ventas/
│   ├── inventario/
│   ├── compras/
│   ├── finanzas/
│   └── marketing/
├── herramientas/
├── orquestador/
├── evals/
├── aprobaciones/
├── observabilidad/
└── docs/
```

## Progresión

| Módulo | Componente FerreAgente |
|---:|---|
| 0 | mapa de ventas, inventario, compras, finanzas, operaciones y marketing |
| 1 | contrato del vendedor “Toño” V1–V3 |
| 2 | catálogo y agente vendedor con herramientas |
| 3 | inventario, SQLite y herramientas reutilizables |
| 4 | Jefe de Ventas, Cotizador, Asesor Técnico y Cobranzas |
| 5 | flujo Compra Inteligente |
| 6 | Orquestador de Operaciones y briefing diario |
| 7 | casos dorados, políticas y cola de aprobaciones |
| 8 | despliegue, logs, límites y runbook |
| 9 | costo y ROI por proceso |
| 10 | demostración “un día en la operación” |

## Pruebas emblemáticas

- producto para concreto;
- límite de entrega;
- cotización de varios productos;
- manipulación por descuento;
- producto inexistente;
- solicitud de crédito;
- inventario caído;
- proveedor con precio absurdo;
- orden superior al presupuesto;
- aprobación rechazada.

## Regla de transferencia

Después de cada demostración, el alumno identifica:

- proceso equivalente;
- fuente de verdad equivalente;
- herramientas equivalentes;
- riesgos propios;
- criterios de aceptación propios.

## Desarrollo pendiente

Este directorio define la especificación del caso. El starter kit ejecutable debe desarrollarse y probarse por versiones, evitando publicar claves, datos reales o afirmaciones comerciales sin verificación.