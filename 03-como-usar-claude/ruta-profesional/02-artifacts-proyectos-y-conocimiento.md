# Bloque 2 · Artifacts, Projects y conocimiento

Este archivo reúne los módulos 2, 3 y 4 de la Ruta profesional.

---

# Módulo 2 · Artifacts y creación de entregables

**Duración:** 2 horas.

## Objetivos

- Diferenciar una respuesta de chat de un entregable reutilizable.
- Crear y refinar Artifacts.
- Diseñar documentos, visualizaciones o prototipos con criterios de aceptación.
- Trabajar por versiones sin perder decisiones anteriores.

## Contenido

### 2.1 De respuesta a producto

Una respuesta sirve para consumir información. Un Artifact sirve para **trabajar sobre un objeto**: editarlo, probarlo, compartirlo o reutilizarlo.

Ejemplos:

- una propuesta comercial;
- un tablero o visualización;
- un simulador educativo;
- una calculadora sencilla;
- un wireframe;
- una guía interactiva;
- un documento operativo.

### 2.2 Brief de un buen Artifact

```text
Usuario y problema
Resultado esperado
Información de entrada
Interacciones necesarias
Reglas y restricciones
Criterios de aceptación
Ejemplo o referencia visual
```

### 2.3 Ciclo de mejora

1. Crear una versión mínima.
2. Probar con un caso real.
3. Registrar fallos y fricciones.
4. Cambiar una dimensión por vez.
5. Volver a probar.
6. Guardar una versión final y una lista de mejoras futuras.

## Práctica guiada

Construir uno de estos entregables:

- calculadora de prioridades;
- generador de brief;
- tablero de seguimiento;
- documento de propuesta editable;
- simulador de preguntas para capacitación.

## Entregable

Artifact funcional más una ficha con objetivo, audiencia, entradas, criterios de aceptación y límites.

---

# Módulo 3 · Projects, instrucciones persistentes y context engineering

**Duración:** 2 horas.

## Objetivos

- Crear un Project con alcance claro.
- Escribir instrucciones mantenibles.
- Diseñar una base de conocimiento mínima y útil.
- Organizar conversaciones sin mezclar procesos o clientes.
- Distinguir contexto permanente, contexto reutilizable y contexto temporal.
- Reducir repetición, ruido y consumo innecesario de contexto.

## Contenido

### 3.1 Cuándo usar un Project

Un Project tiene sentido cuando el trabajo:

- dura varios días o semanas;
- reutiliza las mismas fuentes;
- requiere una voz, proceso o formato estable;
- incluye varias conversaciones relacionadas;
- será compartido por un equipo.

Un Project no es necesario para una pregunta aislada, una traducción puntual o una tarea que no volverá a repetirse.

### 3.2 Anatomía recomendada

```text
Nombre del proyecto
Propósito
Usuarios
Fuentes disponibles
Reglas permanentes
Formatos de salida
Decisiones ya tomadas
Acciones prohibidas
Criterios de calidad
```

### 3.3 Plantilla de instrucciones

```markdown
# Propósito
Este proyecto ayuda a [audiencia] a producir [entregables].

# Contexto
[Situación, organización, producto o proceso.]

# Fuentes
Usa primero los documentos del proyecto. Distingue información de fuente e inferencia.

# Forma de trabajar
1. Confirma el objetivo y el entregable.
2. Señala información faltante.
3. Produce un borrador.
4. Verifica contra los criterios.

# Reglas
- No mezclar información entre clientes.
- No inventar cifras, políticas o citas.
- Pedir aprobación antes de enviar, publicar o comprometer recursos.

# Formato
[Idioma, tono, estructura y longitud.]
```

### 3.4 Arquitectura de conocimiento

No se debe subir todo indiscriminadamente. Clasificar las fuentes:

| Tipo | Ejemplo | Tratamiento |
|---|---|---|
| Fuente de verdad | política vigente, contrato, base oficial | Prioridad máxima y fecha visible |
| Referencia | ejemplos, reportes anteriores | Usar como guía, no como verdad actual |
| Contexto | notas, entrevistas, ideas | Puede contener opiniones o contradicciones |
| Obsoleto | versiones anteriores | Archivar o etiquetar claramente |

Una base de conocimiento útil suele empezar con pocas fuentes bien elegidas. Más documentos no significan automáticamente mejores respuestas.

### 3.5 Organización de conversaciones

Una conversación por objetivo o entregable:

```text
Proyecto: Lanzamiento Q4
├── Investigación
├── Estrategia
├── Propuesta comercial
├── Contenido
└── Seguimiento y decisiones
```

Todas las conversaciones comparten el contexto estable del Project, pero cada una mantiene un objetivo específico y un historial más limpio.

### 3.6 Context engineering y eficiencia de tokens

**Context engineering** es diseñar deliberadamente qué información recibe la IA, en qué lugar vive, cuándo se carga y cómo se mantiene actualizada.

El objetivo no es llenar la ventana de contexto. El objetivo es darle a Claude **la información mínima suficiente para hacer bien el trabajo**.

#### Las tres capas del contexto

```text
PROJECT     = contexto permanente y fuentes compartidas
CONVERSACIÓN = objetivo o entregable específico
MENSAJE      = instrucciones temporales de la tarea actual
```

| Capa | Qué debe contener | Ejemplos |
|---|---|---|
| Project | Información estable y reutilizable | audiencia, propósito, tono, reglas, políticas, fuentes oficiales |
| Conversación | Un proceso u objetivo concreto | investigación, propuesta, campaña, análisis, revisión |
| Mensaje | Lo que cambia en esta ejecución | fecha, archivo puntual, excepción, entregable solicitado |

#### Reglas para usar mejor el contexto

1. **Lo estable va en las instrucciones del Project.** No repetir en cada mensaje el rol, la audiencia, el tono o las reglas permanentes.
2. **Las fuentes reutilizadas van al conocimiento del Project.** Manuales, políticas, brandbooks y documentos oficiales que se consultarán varias veces.
3. **Lo temporal va en el mensaje actual.** La tarea específica, el periodo, el archivo puntual y cualquier excepción.
4. **Una conversación por objetivo.** No mezclar investigación, redacción, revisión y seguimiento en un único chat interminable.
5. **No subir el archivero completo.** Empezar con entre tres y siete fuentes realmente relevantes y ampliar solo cuando haga falta.
6. **Crear resúmenes maestros.** Consolidar decisiones, glosarios o reglas repetidas en un documento breve y vigente.
7. **Eliminar o marcar contenido obsoleto.** Varias versiones contradictorias aumentan el ruido y disminuyen la confiabilidad.
8. **Pedir recuperación selectiva.** Indicar qué fuente, sección o tipo de evidencia debe consultar antes de responder.
9. **Cerrar conversaciones largas con un resumen de continuidad.** Registrar decisiones, pendientes y fuentes usadas antes de abrir una nueva conversación.
10. **Revisar el Project periódicamente.** Actualizar fuentes, retirar duplicados y comprobar que las instrucciones sigan siendo breves y aplicables.

#### Qué significa realmente “ahorrar tokens”

Un Project no garantiza por sí solo un costo menor. El ahorro práctico aparece cuando:

- dejas de repetir el mismo contexto en cada prompt;
- evitas conversaciones innecesariamente largas;
- reduces documentos duplicados o irrelevantes;
- consigues mejores respuestas con menos correcciones;
- separas conocimiento estable de instrucciones temporales;
- recuperas únicamente la información relevante para cada tarea.

La meta pedagógica no debe ser solamente “usar menos tokens”, sino **obtener más calidad por cada unidad de contexto**.

#### Señales de que el contexto está mal diseñado

- Claude mezcla clientes, versiones o proyectos.
- Responde con reglas antiguas.
- Necesitas repetir las mismas instrucciones en cada mensaje.
- Las conversaciones se vuelven largas y difíciles de retomar.
- Hay muchas fuentes, pero Claude no identifica cuál es la oficial.
- La respuesta mejora cuando vuelves a comenzar en un chat limpio.

#### Plantilla de auditoría de contexto

```markdown
# Auditoría del Project

## Qué debe permanecer siempre disponible
- [instrucciones, reglas y fuentes estables]

## Qué debe actualizarse
- [datos, políticas o decisiones con fecha]

## Qué debe retirarse o archivarse
- [duplicados, versiones anteriores, documentos irrelevantes]

## Qué debe vivir en conversaciones separadas
- [objetivos o entregables distintos]

## Criterio de suficiencia
Claude tiene suficiente contexto cuando puede producir [resultado]
sin que yo repita [información estable] y sin consultar material irrelevante.
```

### 3.7 Estrategia de continuidad entre conversaciones

Cuando una conversación ya cumplió su objetivo o acumuló demasiado historial:

1. Pedir un resumen de decisiones, fuentes y pendientes.
2. Guardar ese resumen en el Project como documento de continuidad si será reutilizado.
3. Abrir una conversación nueva con un objetivo específico.
4. Referenciar el resumen y solo las fuentes necesarias.
5. Archivar o nombrar claramente la conversación anterior.

Esto conserva el aprendizaje útil sin arrastrar toda la conversación anterior.

## Práctica guiada

Crear un Project real con:

- instrucciones;
- entre tres y siete fuentes;
- una conversación de análisis;
- una conversación de producción;
- una prueba deliberada sobre información que no está en las fuentes;
- una auditoría de contexto;
- una comparación entre un prompt que repite todo el contexto y otro que aprovecha correctamente el Project.

## Entregable

Project configurado más:

1. inventario de fuentes y reglas de actualización;
2. mapa de las tres capas del contexto;
3. auditoría de contexto;
4. criterio para abrir una conversación nueva;
5. reflexión breve sobre calidad obtenida, repeticiones evitadas y posibles ahorros de contexto.

---

# Módulo 4 · Investigación, datos y trazabilidad

**Duración:** 2 horas.

## Objetivos

- Elegir entre conocimiento del modelo, búsqueda web y documentos internos.
- Formular una pregunta investigable.
- Evaluar calidad, actualidad y concordancia de fuentes.
- Crear un informe que permita rastrear cada afirmación importante.

## Contenido

### 4.1 Tres modos de conocimiento

| Modo | Úsalo para | Riesgo principal |
|---|---|---|
| Conocimiento general | Conceptos estables y explicación | Desactualización o imprecisión |
| Búsqueda / Research | Hechos recientes y fuentes públicas | Fuentes débiles o contradictorias |
| Project / documentos | Información privada o específica | Documentos obsoletos o incompletos |

### 4.2 Pregunta de investigación

Una pregunta fuerte incluye:

- decisión que debe apoyar;
- alcance geográfico o sectorial;
- periodo temporal;
- criterios de comparación;
- fuentes preferidas;
- formato del resultado;
- incertidumbres que deben declararse.

### 4.3 Tabla de evidencia

| Afirmación | Fuente | Fecha | Tipo de fuente | Confianza | Observación |
|---|---|---|---|---|---|

### 4.4 Protocolo de desacuerdo

Cuando dos fuentes difieren:

1. No elegir silenciosamente una.
2. Presentar ambas posiciones.
3. Revisar fecha, metodología y alcance.
4. Explicar cuál parece más aplicable y por qué.
5. Mantener visible la incertidumbre si no puede resolverse.

## Práctica guiada

Investigar una decisión real con al menos tres fuentes y producir:

- resumen ejecutivo;
- tabla de evidencia;
- desacuerdos encontrados;
- vacíos de información;
- recomendación condicionada.

## Entregable

Informe trazable con fuentes, fecha de corte y sección explícita de incertidumbres.
