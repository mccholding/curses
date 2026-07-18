# Módulo 5 · Patrones de coordinación

**Duración:** 5 horas.

## Objetivos

- Comparar patrones multiagente.
- Elegir el patrón mínimo adecuado.
- Diseñar dependencias, verificaciones e idempotencia.
- Entender cómo se componen los errores.

## Patrones principales

### Pipeline

La salida de una etapa alimenta la siguiente.

Útil cuando el orden está claro y cada paso tiene una responsabilidad estable.

### Orquestador–trabajadores

Un componente central descompone, asigna y ensambla.

Útil cuando las subtareas cambian según el objetivo.

### Paralelo con fusión

Varios trabajadores analizan al mismo tiempo y un componente fusiona resultados.

Útil para análisis independientes o cuando se busca reducir latencia.

### Generador–evaluador

Un agente produce y otro evalúa contra criterios explícitos.

Útil para propuestas, reportes, código, campañas y documentos de alta calidad.

### Equipo persistente

Los roles se mantienen entre tareas y acumulan estado o especialización.

Útil solo cuando la continuidad agrega valor y existe una estrategia de memoria.

## Regla de diseño

Construir y probar primero los trabajadores. Conectar después. Evitar redes libres donde todos hablan con todos.

## Composición de errores

La confiabilidad de una cadena disminuye cuando se agregan pasos. Por eso cada etapa debe:

- validar entradas;
- producir una salida estructurada;
- registrar estado;
- poder reintentarse sin duplicar efectos;
- detenerse ante condiciones no autorizadas.

## FerreAgente

Flujo Compra Inteligente:

```text
Inventario detecta necesidades
→ Compras compara proveedores
→ Finanzas evalúa flujo de caja
→ sistema prepara recomendación
→ humano aprueba, recorta o rechaza
```

La orden no se envía automáticamente.

## Transferencia

### Consultora

```text
brief → investigación → solución → estimación → revisión
```

### Academia

```text
diagnóstico → plan → actividad → evaluación → retroalimentación
```

### Ecommerce

```text
incidente → datos del pedido → política → propuesta → aprobación o respuesta
```

## Construcción

Diseñar dos versiones del mismo proceso:

1. workflow estructurado;
2. arquitectura con agentes.

Comparar:

- precisión;
- costo;
- latencia;
- facilidad de depuración;
- flexibilidad;
- riesgo.

## Pruebas

- éxito de punta a punta;
- fallo de un trabajador;
- reintento;
- ejecución duplicada;
- resultado contradictorio;
- límite presupuestal;
- aprobación rechazada.

## Entregable

Un flujo multiagente completo, diagrama de arquitectura y justificación de por qué ese patrón es preferible a una solución más simple.