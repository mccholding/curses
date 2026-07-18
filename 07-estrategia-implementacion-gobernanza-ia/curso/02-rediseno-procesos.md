# Módulo 2 · Rediseño de procesos

## Pregunta directiva

¿Qué debe cambiar en el proceso, en las decisiones y en el rol humano para que la IA genere valor real?

## Objetivos

- mapear el proceso actual antes de automatizar;
- distinguir tareas, decisiones, excepciones y controles;
- diseñar un proceso futuro con responsabilidades claras;
- evitar trasladar ineficiencias a una herramienta más rápida;
- definir qué no debe automatizarse.

## Mapa del proceso actual

Documentar:

- evento de inicio;
- entradas y fuentes;
- pasos y responsables;
- decisiones;
- esperas y transferencias;
- errores y reprocesos;
- excepciones;
- controles;
- resultado final;
- métricas actuales.

## Distribución del trabajo

Cada paso debe clasificarse como:

- humano obligatorio;
- humano asistido por IA;
- automatización determinista;
- workflow con IA;
- agente con autonomía limitada;
- revisión o aprobación humana;
- fuera de alcance.

## Diseño del proceso futuro

El nuevo proceso debe definir:

```text
quién inicia
qué contexto se utiliza
qué puede decidir la IA
qué herramientas puede usar
qué evidencia debe producir
qué acción requiere aprobación
cómo se gestiona una excepción
cómo se registra lo ocurrido
cuándo se detiene o escala
```

## Principio de supervisión significativa

La aprobación humana no consiste en añadir un botón al final. La persona debe disponer de:

- información suficiente;
- tiempo razonable;
- autoridad real para rechazar;
- explicación o evidencia útil;
- procedimiento de escalamiento.

## Taller

Rediseñar un proceso crítico en dos versiones:

1. solución mínima con reglas y asistencia;
2. solución avanzada con mayor autonomía.

Comparar valor, riesgo, costo y complejidad. Elegir la versión mínima que resuelva el problema.

## Entregable

`proceso-futuro-ia.md`

Debe incluir:

- diagrama actual y futuro;
- roles;
- decisiones delegadas y retenidas;
- controles;
- excepciones;
- puntos de aprobación;
- métricas;
- procedimiento de reversión manual.

## Simulación

Analizar tres fallos:

- el modelo responde con confianza pero está equivocado;
- la fuente de datos no está disponible;
- el usuario intenta saltarse una política.

## Error frecuente

Diseñar el proceso alrededor de las funciones de una herramienta específica. Primero se define el modelo operativo; después se selecciona la tecnología.
