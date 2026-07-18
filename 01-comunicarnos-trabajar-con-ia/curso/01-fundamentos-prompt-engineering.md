# Módulo 1 · Fundamentos de Prompt Engineering

**Duración:** 60 minutos.

## Objetivos

- Entender la diferencia entre buscar y dar instrucciones.
- Definir un resultado observable.
- Aportar el contexto inmediato necesario.
- Pedir una salida con formato y límites claros.

## Idea central

Google recupera páginas. Una IA generativa construye una respuesta a partir de la instrucción y el contexto que recibe.

Un prompt útil no necesita ser largo. Necesita eliminar ambigüedad.

## Estructura universal

```text
OBJETIVO
¿Qué resultado necesito?

CONTEXTO
¿Qué debe saber para responder bien?

TAREA
¿Qué acción concreta debe ejecutar?

FORMATO
¿Cómo debe entregar la respuesta?

RESTRICCIONES
¿Qué límites, reglas o exclusiones debe respetar?

CRITERIO DE CALIDAD
¿Cómo sabremos que la respuesta sirve?
```

## Antes y después

**Solicitud vaga**

```text
Hazme un plan de marketing.
```

**Solicitud diseñada**

```text
Crea un plan de marketing de 30 días para una panadería de barrio que quiere aumentar pedidos por WhatsApp.

Audiencia: familias y trabajadores que viven a menos de 3 km.
Presupuesto: máximo USD 300.
Canales disponibles: Instagram, WhatsApp y alianzas locales.

Entrégalo en una tabla con semana, objetivo, acción, canal, responsable y métrica.
No propongas publicidad en televisión ni influencers nacionales.
El plan debe poder ejecutarlo una sola persona dedicando 5 horas semanales.
```

## Errores frecuentes

- pedir un tema en lugar de un entregable;
- omitir audiencia y propósito;
- pedir “algo profesional” sin definir qué significa;
- mezclar varias tareas incompatibles;
- no indicar longitud ni formato;
- asumir que la IA conoce información que nunca recibió.

## Práctica guiada

Reescribir tres solicitudes vagas:

1. “Resume este documento”.
2. “Escribe un correo”.
3. “Ayúdame con mi presentación”.

Cada versión debe incluir objetivo, contexto, formato, restricciones y criterio de calidad.

## Entregable

Un prompt aplicado a una tarea real del alumno, acompañado de:

- resultado esperado;
- información que la IA necesita;
- criterio para evaluar la respuesta.

## Checklist rápido

Antes de enviar:

- ¿pedí un resultado y no solo un tema?
- ¿la audiencia está clara?
- ¿incluí la información que no puede adivinar?
- ¿definí el formato?
- ¿establecí límites?
- ¿puedo comprobar si la respuesta cumple?