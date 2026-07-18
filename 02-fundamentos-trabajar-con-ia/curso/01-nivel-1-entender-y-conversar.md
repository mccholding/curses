# 🟢 NIVEL 1 — ENTENDER Y CONVERSAR
*Lo fundamental: qué es esta tecnología y cómo hablarle bien.*

## 1.1 ¿Qué es un LLM?

**LLM** significa *Large Language Model* (Modelo de Lenguaje de Gran Escala). Es el "cerebro" detrás de Claude, ChatGPT o Gemini.

### La explicación sencilla

Imagina una persona que leyó **millones de libros, artículos, páginas web y código**. No memorizó todo palabra por palabra, pero desarrolló una intuición extraordinaria sobre cómo se conectan las ideas, cómo se escribe bien y cómo se resuelven problemas.

Un LLM es eso en forma de programa: un modelo matemático entrenado con enormes cantidades de texto que aprendió a **predecir cuál es la mejor siguiente palabra** dada una conversación. Haciéndolo millones de veces por segundo, produce respuestas completas, coherentes y útiles.

### Cuatro verdades que debes grabarte

| Verdad | Qué significa en la práctica |
|---|---|
| **No "busca" en internet por defecto** | Responde con lo que aprendió en su entrenamiento. La búsqueda web es una capacidad extra que algunas herramientas le agregan (ver 1.7). |
| **No tiene memoria permanente por defecto** | Cada conversación empieza "de cero", salvo que la herramienta tenga funciones de memoria. |
| **Puede equivocarse con total confianza** | A veces inventa datos que suenan correctos (ver 1.4). |
| **El contexto lo es todo** | Mientras más claro y completo sea lo que le das, mejor responde (ver 1.2 y 1.6). |

> 🎯 **Hazlo tú ahora (3-5 min):** pregúntale a la IA algo de tu especialidad que TÚ domines a la perfección. Evalúa su respuesta como el experto que eres. Descubrirás en carne propia su nivel real: dónde brilla y dónde patina.
>
> ⚠️ **Error común:** creer que "lo sabe todo" porque respondió con seguridad. La seguridad del tono no es garantía de exactitud.
>
> ✅ **Buena práctica:** trátala como a un colega brillante recién llegado: aprovéchala muchísimo, pero valida lo crítico antes de firmarlo.


---

## 1.2 Tokens y ventana de contexto: la "memoria de trabajo" de la IA

Estos dos términos explican comportamientos que seguro ya has notado en el chat.

### ¿Qué es un token?

La IA no lee palabras: lee **tokens**, que son pedazos de texto. Un token es aproximadamente ¾ de una palabra en promedio:

```
"Hola, ¿cómo estás hoy?"  →  [Hola] [,] [¿cómo] [estás] [hoy] [?]  ≈ 6 tokens
```

Todo se mide en tokens: lo que tú escribes, los archivos que subes, y lo que la IA responde. Los tokens son la "unidad de medida" (y de costo) del mundo de la IA.

### ¿Qué es la ventana de contexto?

Es la **memoria de trabajo** de la IA: la cantidad máxima de tokens que puede "tener presentes" a la vez en una conversación. Incluye TODO: tus mensajes, sus respuestas, los archivos subidos, las instrucciones.

### La analogía del escritorio 🗒️

Imagina que la IA trabaja en un escritorio de tamaño fijo:

- Cada mensaje y cada archivo es un papel que pones sobre el escritorio
- Mientras haya espacio, la IA ve todos los papeles y trabaja perfecto
- Cuando el escritorio se llena, los papeles más viejos **se caen** — y la IA empieza a "olvidar" el inicio de la conversación

### Por qué esto te importa (mucho)

1. **Explica por qué las conversaciones largas se degradan:** la IA no "se cansó"; su escritorio se llenó.
2. **Explica por qué conviene una conversación nueva por tema:** escritorio limpio = mejor rendimiento.
3. **Explica por qué "menos es más" al subir archivos:** sube lo relevante, no todo el archivero.
4. **Explica comandos que verás después** como `/compact` (comprimir la conversación) y `/clear` (limpiar el escritorio) en Claude Code.

> 💡 Dato útil: los modelos modernos tienen ventanas enormes (cientos de miles de tokens, y algunos hasta 1 millón). Pero incluso con ventanas gigantes, la información en medio de un contexto muy largo se aprovecha peor que la del inicio y el final. **Contexto enfocado siempre gana a contexto gigante y desordenado.**

> 🎯 **Hazlo tú ahora (3-5 min):** abre una conversación vieja y muy larga y pregunta algo que mencionaste al inicio. Observa el resultado. Luego abre una conversación nueva, pega solo lo relevante y repite la pregunta. Compara.
>
> ⚠️ **Error común:** pegar 80 páginas de manual y preguntar por un detalle de la página 3. La IA no es tonta: su escritorio quedó sepultado.
>
> ✅ **Buena práctica:** una conversación por tema, y sube lo relevante, no el archivero completo. Escritorio limpio = mejores respuestas.


---

## 1.3 Los modelos y sus diferencias: ¿por qué hay varios?

Habrás visto nombres como **Haiku, Sonnet y Opus** (en Claude) o los equivalentes de otras marcas. No es marketing: son modelos con distinta **potencia, velocidad y costo**.

### La analogía del transporte 🚗

| Modelo (Claude) | Analogía | Cuándo usarlo |
|---|---|---|
| **Haiku** | Motocicleta: rapidísima y barata | Tareas simples y masivas: clasificar, resumir, respuestas rápidas |
| **Sonnet** | Auto: el equilibrio perfecto | El día a día: redacción, análisis, la mayoría de los proyectos |
| **Opus / Fable** | Camión de carga pesada: máxima potencia | Problemas complejos: razonamiento profundo, proyectos grandes, código difícil |

### La regla práctica

> **Usa el modelo más pequeño que haga bien la tarea.** No necesitas el camión para ir por el pan. Cuando trabajes en herramientas que te dejan elegir modelo (como Claude Code con el comando `/model`), elegir bien ahorra tiempo y dinero.

> 🎯 **Hazlo tú ahora (3-5 min):** haz la misma pregunta sencilla a dos modelos distintos (si tu herramienta lo permite) y compara velocidad y calidad. Sentirás la diferencia moto/auto/camión.
>
> ⚠️ **Error común:** usar siempre el modelo más potente "por si acaso" (lento y más caro), o el más rápido para un problema que necesita razonamiento profundo.
>
> ✅ **Buena práctica:** modelo pequeño por defecto; escala solo si el resultado no alcanza la calidad que necesitas.


---

## 1.4 Alucinaciones: el riesgo número uno

### La explicación sencilla

Una **alucinación** es cuando la IA **inventa información que suena perfectamente correcta pero es falsa**: una cifra, una fecha, una cita, una ley, una fuente que no existe.

¿Por qué pasa? Recuerda: el LLM predice la siguiente palabra más probable. Cuando no sabe algo, no siempre dice "no sé" — a veces genera la respuesta que *suena* más plausible. Y lo hace con el mismo tono seguro de siempre.

### Las reglas de oro de la verificación

1. **A mayor importancia, mayor verificación.** ¿Un poema? Relájate. ¿Una cifra para un reporte a dirección? Verifica.
2. **Pide fuentes y revísalas.** "Dame la fuente de ese dato" — y confirma que la fuente exista y diga eso.
3. **Datos recientes = activar búsqueda web** (ver 1.7). El conocimiento de entrenamiento tiene fecha de corte.
4. **Desconfía especialmente de:** cifras exactas, citas textuales, nombres de leyes/artículos, referencias bibliográficas y eventos recientes.
5. **La IA es un colaborador brillante, no un oráculo.** Tú firmas el trabajo final; tú verificas.

> 🎯 **Hazlo tú ahora (3-5 min):** pide a la IA 3 datos con cifras de tu industria, con fuentes. Verifica UNA fuente: ¿existe? ¿dice eso? Este ejercicio de 5 minutos vale más que cualquier advertencia teórica.
>
> ⚠️ **Error común:** copiar una cita textual o cifra directo a un documento oficial. Ha pasado en la vida real: profesionales sancionados por citar jurisprudencia o referencias que la IA inventó.
>
> ✅ **Buena práctica:** regla del semáforo: todo lo que se publica, se firma o decide dinero/salud/reputación, se verifica siempre contra la fuente.


---

## 1.5 Chat con IA: el punto de partida

El **chat** es la forma más conocida de usar un LLM: escribes, la IA responde. Es la opción #1 de tu caja de herramientas — y para muchísimas tareas, es todo lo que necesitas.

### Qué SÍ hace muy bien el chat

- Redactar y corregir (emails, propuestas, resúmenes)
- Explicar conceptos y responder preguntas
- Traducir, resumir, reformatear
- Analizar documentos e imágenes que subes
- Ayudarte a pensar: ideas, pros y contras, planes

### Qué NO puede hacer el chat por sí solo

Aquí nace el resto del curso. El chat básico:

- ❌ No se **conecta a tus herramientas** (correo, calendario, base de datos) → lo resuelve **MCP** (Nivel 2)
- ❌ No conoce **tu forma de trabajar** y se lo repites todo cada vez → lo resuelven las **Skills** (Nivel 2)
- ❌ No **ejecuta proyectos de muchos pasos** por sí solo → lo resuelven los **agentes y Cowork** (Nivel 3)
- ❌ No trabaja **en tus carpetas y archivos locales** → lo resuelve **Claude Code** (Nivel 4)
- ❌ No hace nada **sin que tú se lo pidas cada vez** → lo resuelven las **tareas programadas y los loops** (Niveles 3 y 4)

**Cada limitación del chat tiene nombre y solución. Ese es el mapa del curso.**

> 🎯 **Hazlo tú ahora (3-5 min):** haz una lista de 5 tareas que hiciste la semana pasada y marca cuáles habrías resuelto (total o parcialmente) con el chat. Casi siempre salen 2 o 3 sorpresas.
>
> ⚠️ **Error común:** abandonar después de una mala respuesta ("esto no sirve"). El chat es una conversación, no una máquina expendedora: la segunda instrucción casi siempre mejora a la primera.
>
> ✅ **Buena práctica:** si la respuesta no sirvió, no repitas la pregunta: reformúlala con más contexto o pide los ajustes específicos que quieres.


---

## 1.6 Prompt engineering: el arte de pedir bien

Un **prompt** es la instrucción que le das a la IA. El **prompt engineering** es el conjunto de técnicas para escribir instrucciones que producen mejores resultados. Es la habilidad de mayor retorno inmediato de todo el Nivel 1.

### La fórmula de los 5 ingredientes

Un buen prompt suele tener estos elementos (no siempre todos, pero conócelos):

```
1. ROL       →  "Eres un analista financiero senior..."
2. CONTEXTO  →  "...trabajas para una PyME de retail. Adjunto las ventas del Q1."
3. TAREA     →  "Analiza las tendencias y detecta riesgos."
4. FORMATO   →  "Entrégalo como reporte de 1 página: resumen, 3 hallazgos, 2 recomendaciones."
5. EJEMPLO   →  "Aquí un reporte anterior para que copies el estilo: [...]"
```

### Comparación directa

**Prompt débil:**
```
Hazme un reporte de ventas
```

**Prompt fuerte:**
```
Eres un analista de ventas senior. Con los datos adjuntos del
primer trimestre, crea un reporte de 1 página con: resumen
ejecutivo, las 3 tendencias principales y 2 recomendaciones
concretas. Tono profesional, en español, cifras en pesos.
Sigue el estilo del reporte de ejemplo que te adjunto.
```

### Técnicas que multiplican resultados

| Técnica | Cómo se ve |
|---|---|
| **Pedir el plan primero** | "Antes de hacerlo, dime cómo lo vas a abordar" |
| **Pensar paso a paso** | "Razona paso a paso antes de dar la respuesta final" |
| **Dar ejemplos (few-shot)** | "Aquí van 2 ejemplos del formato que quiero: ..." |
| **Definir lo que NO quieres** | "No uses lenguaje técnico. No excedas 300 palabras." |
| **Iterar** | El primer resultado es un borrador: "Bien, ahora hazlo más directo y agrega X" |
| **Pedirle que pregunte** | "Si te falta información para hacerlo bien, pregúntame antes de empezar" |

> 🔮 **Adelanto importante:** en el Nivel 4 verás que la industria ya habla de la evolución de esta habilidad: primero fue *prompt engineering* (escribir bien la instrucción), luego *context engineering* (preparar bien todo el contexto), y hoy la frontera es *loop engineering* (diseñar sistemas que generan sus propias instrucciones). Pero todo empieza aquí: **un mal prompt dentro de un sistema sofisticado solo produce basura más rápido.**

> 🎯 **Hazlo tú ahora (3-5 min):** toma el último correo o mensaje difícil que escribiste. Pídeselo a la IA primero con un prompt de una línea, y luego con la fórmula de 5 ingredientes. Compara los dos resultados: esa diferencia es el retorno del prompt engineering.
>
> ⚠️ **Error común:** el prompt telegráfico + esperar lectura de mente ("hazme un reporte") y culpar a la IA del resultado genérico.
>
> ✅ **Buena práctica:** guarda tus mejores prompts en un documento personal. Son activos reutilizables — y la semilla de tus futuras Skills (Nivel 2).


---

## 1.7 Búsqueda web y RAG: cuando la IA sale a buscar información

### El problema que resuelven

El LLM aprendió de textos hasta una **fecha de corte**. No sabe qué pasó ayer, ni conoce los documentos privados de tu empresa. Dos tecnologías resuelven esto:

### Búsqueda web

La IA hace búsquedas en internet en tiempo real, lee los resultados y responde con información actual **citando fuentes**. Ya viene integrada en Claude y la mayoría de los chats modernos.

**Cuándo activarla / pedirla:** precios actuales, noticias, datos de empresas, cualquier cosa que cambie con el tiempo. Un buen hábito: *"Busca en la web la información más reciente sobre X antes de responder."*

### RAG (Retrieval-Augmented Generation)

**RAG** = "Generación Aumentada por Recuperación". Es la técnica de darle a la IA acceso a **una base de documentos específica** (los manuales de tu empresa, tus contratos, tu base de conocimiento) para que **recupere** los fragmentos relevantes y responda basándose en ellos.

### La analogía del examen 📚

- **LLM solo** = examen a libro cerrado: responde de memoria (y puede alucinar)
- **Búsqueda web** = examen con acceso a internet: consulta el mundo
- **RAG** = examen a libro abierto con TUS libros: consulta tus documentos

### Por qué importa para tus proyectos

Cuando en tu empresa alguien diga "queremos un chatbot que responda con nuestros documentos internos", eso es RAG. Cuando subes archivos a un Proyecto de Claude para que siempre los tenga de referencia, estás usando la misma idea. **RAG reduce alucinaciones porque la IA responde con base en fuentes reales que puede citar.**

> 🎯 **Hazlo tú ahora (3-5 min):** pregunta algo reciente de tu industria SIN pedir búsqueda, y luego pidiendo explícitamente "busca en la web antes de responder". Compara las dos respuestas y las fuentes.
>
> ⚠️ **Error común:** pedir datos de hoy (precios, noticias, personas en cargos) sin activar búsqueda, y confiar en una respuesta que viene de la memoria de entrenamiento.
>
> ✅ **Buena práctica:** hazte siempre la pregunta "¿esto pudo cambiar desde su entrenamiento?" Si sí → pide búsqueda. Si es sobre TUS documentos → piensa en RAG o Proyectos.


---

### ✅ Checkpoint del Nivel 1

Ya puedes explicar: qué es un LLM, por qué la IA "olvida" (contexto), por qué hay varios modelos, por qué verificar (alucinaciones), cómo pedir bien (prompts) y cómo darle información actual o privada (web/RAG). **Con solo esto ya eres mejor usuario que el 90% de las personas.** Ahora vamos a darle superpoderes.

---
---
