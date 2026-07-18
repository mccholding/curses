# Módulo 5 · Loop Engineering

**Duración:** 75 minutos.

## Objetivos

- Entender el ciclo básico de un sistema agéntico.
- Diseñar verificación y corrección antes de automatizar.
- Definir una condición de parada.
- Incorporar límites y checkpoints humanos.

## Definición

**Loop engineering** es diseñar cómo una IA avanza por una tarea, observa el resultado, verifica si cumple, corrige cuando falla y decide cuándo detenerse.

No significa dejar a la IA trabajando indefinidamente. Un buen loop tiene límites claros.

## Estructura mínima

```text
OBJETIVO
   ↓
EJECUTAR
   ↓
VERIFICAR
   ↓
¿CUMPLE?
├── No → diagnosticar → corregir → volver a verificar
└── Sí → entregar → detenerse
```

## Componentes de un loop confiable

| Componente | Pregunta |
|---|---|
| Objetivo | ¿Qué resultado observable debe alcanzar? |
| Entradas | ¿Qué información y herramientas puede usar? |
| Acción | ¿Qué debe ejecutar en cada paso? |
| Estado | ¿Qué debe registrar para no repetir trabajo? |
| Verificador | ¿Cómo comprueba que el resultado sirve? |
| Corrección | ¿Qué hace cuando algo falla? |
| Condición de parada | ¿Cuándo termina? |
| Límite | ¿Cuántos intentos, tiempo o recursos puede usar? |
| Checkpoint humano | ¿Qué decisiones requieren aprobación? |

## Ejemplo no técnico

Tarea: preparar un reporte semanal.

```text
1. Leer los datos disponibles.
2. Validar columnas, periodo y datos faltantes.
3. Si falta información crítica, detenerse y preguntar.
4. Calcular métricas.
5. Crear el reporte con la plantilla aprobada.
6. Comparar cifras del reporte contra la fuente.
7. Verificar secciones obligatorias.
8. Corregir incumplimientos.
9. Repetir la verificación, máximo 3 veces.
10. Solicitar aprobación antes de enviar.
```

## Condiciones de parada

Un loop debe detenerse cuando ocurre alguna de estas situaciones:

- todos los criterios están cumplidos;
- falta información crítica;
- se alcanza el máximo de intentos;
- aparece un riesgo o decisión no autorizada;
- el costo o tiempo excede el límite;
- el verificador no puede determinar la calidad.

## Checkpoints humanos

La IA debe pedir aprobación antes de:

- enviar o publicar;
- comprometer dinero o recursos;
- modificar datos sensibles;
- aceptar condiciones legales;
- eliminar información;
- actuar en nombre de una persona;
- tomar decisiones de alto impacto.

## Loops defectuosos

- “Sigue intentando hasta que funcione” sin límite.
- Verificar con el mismo criterio vago usado para generar.
- Corregir sin registrar qué falló.
- Repetir toda la tarea cuando solo falló una parte.
- Continuar aunque falte información.
- Confundir actividad con progreso.

## Práctica guiada

Elegir una tarea recurrente y documentar:

1. objetivo;
2. entradas;
3. pasos;
4. verificador;
5. corrección;
6. condición de parada;
7. límite de intentos;
8. checkpoint humano.

La práctica se diseña en lenguaje natural. No requiere programación.

## Entregable

Diagrama o runbook de un loop real, acompañado de una explicación de riesgos, límites y decisiones reservadas a una persona.