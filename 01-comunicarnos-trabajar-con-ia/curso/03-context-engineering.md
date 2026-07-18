# Módulo 3 · Context Engineering

**Duración:** 75 minutos.

## Objetivos

- Entender que el contexto es un recurso limitado.
- Identificar la información mínima suficiente.
- Separar contexto permanente, reutilizable y temporal.
- Evitar duplicados, ruido y contradicciones.

## Definición

**Context engineering** es diseñar deliberadamente qué información recibe la IA, dónde vive, cuándo se carga y cómo se mantiene actualizada.

La meta no es darle toda la información disponible. La meta es darle **la información mínima suficiente para hacer bien el trabajo**.

## Las tres capas

```text
ESPACIO O PROJECT = contexto permanente y fuentes compartidas
CONVERSACIÓN      = objetivo o entregable específico
MENSAJE           = instrucciones temporales de esta ejecución
```

| Capa | Contenido recomendado | Ejemplos |
|---|---|---|
| Project o espacio | información estable | propósito, audiencia, tono, políticas, glosario |
| Conversación | un objetivo concreto | investigación, propuesta, análisis, revisión |
| Mensaje | condiciones cambiantes | fecha, archivo puntual, excepción, formato de esta entrega |

## Contexto mínimo suficiente

Antes de agregar información, preguntar:

1. ¿La IA necesita esto para tomar una decisión o producir el entregable?
2. ¿La información sigue vigente?
3. ¿Existe una fuente más breve o más oficial?
4. ¿Debe estar siempre disponible o solo en esta tarea?
5. ¿Contradice otra instrucción o documento?

## Arquitectura de fuentes

| Tipo | Ejemplo | Tratamiento |
|---|---|---|
| Fuente de verdad | política vigente, contrato, base oficial | prioridad máxima y fecha visible |
| Referencia | ejemplos aprobados, reportes anteriores | guía de estilo o estructura |
| Contexto | entrevistas, notas, hipótesis | puede contener opiniones |
| Temporal | datos del mes, campaña actual | actualizar o retirar al terminar |
| Obsoleto | versiones anteriores | archivar o etiquetar claramente |

## Qué significa ahorrar tokens

No se trata únicamente de pagar menos. Se trata de obtener más calidad por cada unidad de contexto.

El ahorro práctico aparece cuando:

- dejas de repetir instrucciones estables;
- eliminas documentos duplicados;
- abres una conversación por objetivo;
- utilizas resúmenes maestros;
- retiras versiones obsoletas;
- consigues una respuesta útil con menos correcciones.

## Señales de contexto deficiente

- la IA mezcla clientes o proyectos;
- utiliza una política anterior;
- necesitas repetir las mismas reglas;
- el chat es difícil de retomar;
- hay muchas fuentes, pero ninguna está marcada como oficial;
- reiniciar la conversación mejora notablemente el resultado.

## Práctica guiada

Para una tarea real, clasificar toda la información disponible en:

```text
Debe permanecer disponible
Debe consultarse solo cuando sea relevante
Debe incluirse en el mensaje actual
Debe retirarse o archivarse
```

Después, probar la tarea con:

1. un prompt que repite todo;
2. un contexto organizado por capas.

Comparar claridad, longitud, correcciones y calidad del resultado.

## Entregable

Mapa de contexto con:

- propósito;
- fuentes oficiales;
- instrucciones estables;
- información temporal;
- contenido excluido;
- regla de actualización;
- criterio de suficiencia.