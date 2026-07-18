# Módulo 4 · Subagentes y especialización

**Duración:** 4 horas.

## Objetivos

- Decidir cuándo dividir un agente en especialistas.
- Diseñar subagentes con alcance y salida acotados.
- Mantener contexto limpio y costos controlados.
- Probar cada trabajador antes de conectarlo.

## Cuándo dividir

Conviene crear especialistas cuando:

- una tarea requiere conocimientos o herramientas diferentes;
- el agente principal acumula demasiadas instrucciones;
- existen subtareas que pueden probarse por separado;
- algunas tareas pueden usar modelos más económicos;
- se necesita aislar permisos o datos.

No conviene dividir cuando una función sencilla o un workflow resuelve el proceso.

## Contrato de un subagente

Todo subagente debe declarar:

- tarea exacta;
- entradas;
- herramientas permitidas;
- formato de salida;
- límite de tiempo o intentos;
- errores esperados;
- criterio de finalización.

Regla: el subagente devuelve resultados al agente padre. No mantiene una conversación paralela con el usuario.

## FerreAgente

El Jefe de Ventas coordina:

- Cotizador;
- Asesor Técnico;
- Cobranzas.

Solicitud de prueba:

> Necesito materiales para una obra, quiero saber si llegan el viernes y cuánto debo actualmente.

El agente padre debe identificar subtareas, invocar únicamente los especialistas necesarios y entregar una respuesta unificada.

## Transferencia

### Consultora

- investigador;
- diseñador de solución;
- estimador de esfuerzo;
- revisor de propuesta.

### Academia

- diagnosticador;
- tutor;
- creador de actividades;
- evaluador.

### Ecommerce

- recomendador;
- estado de pedido;
- devoluciones;
- fidelización.

## Fallos comunes

- Descripciones casi idénticas que confunden el enrutamiento.
- Subagentes que responden directamente al usuario.
- Salidas libres imposibles de combinar.
- Demasiados especialistas para una tarea simple.
- Compartir todo el historial con todos los trabajadores.
- No definir qué ocurre si un especialista falla.

## Construcción

```text
agentes/agente-padre.*
agentes/especialistas/especialista-1.*
agentes/especialistas/especialista-2.*
agentes/especialistas/especialista-3.*
evals/especialistas/
```

## Pruebas

1. tarea que requiere un solo especialista;
2. tarea que requiere dos;
3. tarea que no requiere ninguno;
4. especialista con información insuficiente;
5. especialista que devuelve un error;
6. conflicto entre dos resultados;
7. síntesis final sin duplicaciones.

## Entregable

Agente padre con dos o tres especialistas, pruebas individuales y una prueba integrada con una única respuesta final.