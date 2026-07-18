# 🟠 NIVEL 3 — DELEGAR TRABAJO
*De "responde mi pregunta" a "hazte cargo de este proyecto".*

## 3.1 Agentes: la IA que actúa

### La explicación sencilla

Un **agente** es una IA que no solo responde: **actúa**. Le das un objetivo y el agente planea los pasos, usa herramientas, evalúa resultados, corrige el rumbo y entrega.

La diferencia con el chat es como la diferencia entre preguntar *"¿cómo se organiza un viaje?"* (chat) y decir *"organízame el viaje: busca vuelos, compara hoteles y ármame el itinerario"* (agente).

### Comparación directa

**En chat (tú haces el trabajo, la IA asesora):**
```
Tú: ¿Qué debe llevar un análisis de competencia?
IA: Precios, productos, presencia digital...
Tú: ¿Y cómo comparo precios?
IA: Con una tabla que...
(y tú buscas los datos, haces la tabla, escribes el documento)
```

**Con agente (la IA hace el trabajo, tú supervisas):**
```
Tú: Haz un análisis de competencia de estas 3 empresas:
    busca su información pública, compara precios y productos,
    y entrégame un documento con conclusiones y fuentes.

Agente: [busca] → [organiza] → [compara] → [redacta] →
        "Listo. Aquí está el análisis con fuentes citadas."
```

> 🎯 **Hazlo tú ahora (3-5 min):** toma una tarea que hayas resuelto con 10 preguntas sueltas al chat y reescríbela como UNA sola delegación: objetivo + contexto + criterio de terminado. Guárdala: la usarás en los proyectos.
>
> ⚠️ **Error común:** delegar objetivos vagos ("mejora esto", "analiza la competencia") y culpar al agente del resultado. Lo vago de entrada sale vago de salida.
>
> ✅ **Buena práctica:** delega como delegarías a una persona: objetivo claro, contexto suficiente, entregable definido y límites explícitos.


---

## 3.2 El loop del agente (el concepto que conecta todo el curso)

Este es posiblemente el diagrama más importante del curso. **Todos** los agentes del mundo — de todas las empresas — funcionan con el mismo ciclo, llamado **loop del agente** (*agent loop*):

```
   OBJETIVO
      ↓
  ┌─ OBSERVAR: ¿cuál es la situación actual?
  │     ↓
  │  PLANEAR: ¿cuál es el siguiente paso?
  │     ↓
  │  ACTUAR: usar una herramienta (buscar, leer, escribir, ejecutar)
  │     ↓
  │  VERIFICAR: ¿funcionó? ¿qué aprendí?
  │     ↓
  └── ¿Se cumplió el objetivo? NO → repetir │ SÍ → ENTREGAR
```

De hecho, el equipo de ingeniería de Anthropic describe a los agentes de forma casi humilde: en esencia son un LLM usando herramientas en un ciclo, guiado por la retroalimentación del entorno. Toda la magia está en ese ciclo repetido.

### Qué te enseña este diagrama sobre cómo delegar

Para que un agente trabaje bien necesita **tres cosas de tu parte**:

1. **Un objetivo claro** → "analiza la competencia" es vago; "compara precios y productos de A, B y C, y entrégame recomendaciones" es delegable
2. **Un criterio de "terminado"** → ¿cómo sabrá que ya acabó? "El documento debe incluir X, Y, Z"
3. **Acceso a herramientas** → aquí conectan MCP, Skills y todo el Nivel 2

> 🔮 **Guarda este diagrama en tu memoria.** En el Nivel 4 (sección 4.6) verás que la frontera actual de la industria es precisamente diseñar y encadenar estos loops. Quien entiende el loop, entiende hacia dónde va todo.

> 🎯 **Hazlo tú ahora (3-5 min):** pide una tarea de varios pasos (por ejemplo, "investiga X y prepárame una comparativa") y OBSERVA el ciclo en acción: qué busca, qué decide, cómo se corrige. Verás el diagrama en vivo.
>
> ⚠️ **Error común:** microgestionar cada paso del agente, interrumpiéndolo constantemente. Pierdes justo el beneficio de delegar.
>
> ✅ **Buena práctica:** tú defines el QUÉ y el CUÁNDO ESTÁ LISTO; deja el CÓMO al agente. Revisa al final (o en checkpoints), no en cada micro-paso.


---

## 3.3 Subagentes: equipos de especialistas

### La explicación sencilla

Un **subagente** es un agente especializado al que el agente principal le **delega una parte del trabajo**. Es la diferencia entre un empleado que hace todo y un **equipo** donde cada quien tiene su especialidad.

```
              [AGENTE PRINCIPAL]  ← recibe tu objetivo y coordina
               /       |        \
   [Investigador]  [Analista]  [Redactor]
    busca info      compara      escribe el
    con fuentes     y concluye   informe final
```

### Por qué funciona mejor que un solo agente

1. **Contexto limpio:** cada subagente tiene su propio "escritorio" (¿recuerdas 1.2?) — no se satura con información de otras partes del trabajo
2. **Especialización:** instrucciones enfocadas producen mejores resultados que instrucciones genéricas
3. **Paralelismo:** varios subagentes pueden trabajar al mismo tiempo
4. **Objetividad:** un subagente puede **revisar** el trabajo de otro (nadie es buen juez de su propia tarea — esto reaparece en los loops del Nivel 4)

> ⚠️ **El costo de los equipos:** más agentes = más tokens = más costo. Datos publicados por Anthropic estiman que un chat normal cuesta 1x, un agente con herramientas ~4x y un sistema multiagente ~15x. La regla: usa equipos de agentes cuando la complejidad del proyecto lo justifique, no por moda.

> 🎯 **Hazlo tú ahora (3-5 min):** piensa en tu proyecto actual más importante: si contrataras un mini-equipo humano para hacerlo, ¿qué 3 roles necesitarías? Escríbelos. Esos son exactamente tus futuros subagentes.
>
> ⚠️ **Error común:** el mega-agente que investiga, analiza, redacta y revisa todo él solo: su contexto se satura y la calidad cae en todas las tareas a la vez.
>
> ✅ **Buena práctica:** un rol claro por agente — y agrega siempre un revisor separado del hacedor: nadie es buen juez de su propio trabajo.


---

## 3.4 Cowork: delegar proyectos de oficina completos

**Claude Cowork** es la aplicación de escritorio de Anthropic para **trabajo de conocimiento agéntico**: delegarle a Claude tareas completas de oficina (no de programación) y dejar que las ejecute de principio a fin.

### La diferencia con el chat

| Chat (Claude.ai) | Cowork |
|---|---|
| Conversas y te responde | Le asignas una **tarea completa** y la ejecuta |
| Tú copias/pegas resultados | Trabaja con **carpetas y archivos reales** |
| Un intercambio a la vez | Encadena **muchos pasos** de forma autónoma |
| Ideal para preguntas y redacción | Ideal para **proyectos**: reportes, análisis, organización |

### La explicación sencilla

Si el chat es "conversar con un experto", Cowork es **"sentar a un colaborador en el escritorio de al lado"**. Le das acceso a una carpeta, le describes el proyecto, y Claude lee los archivos, investiga en la web si hace falta, usa las herramientas conectadas (Excel, PowerPoint, Chrome, tus conectores MCP) y te deja los entregables listos en tu carpeta.

### Ejemplo práctico

```
Tú (en Cowork): En esta carpeta hay 40 facturas en PDF.
    Extrae de cada una: proveedor, fecha, concepto y monto.
    Crea un Excel con todo, agrupa por proveedor, y hazme
    un resumen de en qué estamos gastando más.

Claude: [lee los 40 PDFs] → [extrae datos] → [crea el Excel] →
        [redacta el resumen] →
        "Listo: 'facturas-enero.xlsx' y 'resumen.md' en tu carpeta."
```

En chat esto sería subir archivos uno por uno. En Cowork es **una instrucción**.

> 🧭 **Ubicación en el mapa:** Cowork es el punto medio perfecto. Más poder que el chat, sin necesidad de terminal. Para la mayoría de las personas de perfil no técnico, **Cowork es el destino natural de este curso** — el Nivel 4 es para quienes quieren aún más control.

> 🎯 **Hazlo tú ahora (3-5 min):** elige tu carpeta más caótica (esa que te da pereza abrir) y conviértela en tu primer encargo a Cowork: "organiza, clasifica y dime qué requiere mi atención".
>
> ⚠️ **Error común:** estrenar la delegación con lo más crítico de la empresa. Si sale mal, culparás a la herramienta; si sale bien, no sabrás por qué.
>
> ✅ **Buena práctica:** primeras delegaciones de bajo riesgo, y revisa los entregables como revisarías el trabajo de un colaborador nuevo en su primera semana.


---

## 3.5 Tareas programadas: que suceda solo

### La explicación sencilla

Una **tarea programada** es una instrucción que la IA ejecuta **automáticamente en un horario**, sin que estés presente. Es pasar de "le pido cuando me acuerdo" a "sucede solo".

### Ejemplos

| Frecuencia | Tarea |
|---|---|
| Cada mañana 7:00 | "Resume mis correos nuevos y mi agenda del día" |
| Cada lunes | "Prepara el borrador del reporte semanal con los datos de /ventas" |
| Fin de mes | "Consolida las facturas del mes en un Excel con totales" |
| Cada viernes | "Revisa los pendientes incompletos y proponme el plan de la próxima semana" |

### El cambio de mentalidad 🧠

> **Deja de pensar "¿qué le pregunto a la IA?" y empieza a pensar "¿qué trabajo repetitivo hago yo que podría suceder solo?"**

La fórmula:

```
Tarea repetitiva + instrucciones claras + horario = trabajo que ya no haces tú
```

> 🎯 **Hazlo tú ahora (3-5 min):** anota 3 tareas que repites cada semana. Elige la más simple y escríbele su instrucción completa, como si se la fueras a dictar a la IA una sola vez y para siempre.
>
> ⚠️ **Error común:** programar algo que nunca probaste manualmente. La automatización amplifica lo que ya funciona — y también lo que no.
>
> ✅ **Buena práctica:** regla de las 3 veces: primero se hace manual con la IA → cuando funciona 3 veces seguidas → entonces se programa. Y revisa los resultados los primeros ciclos.


---

### ✅ Checkpoint del Nivel 3

Ya sabes delegar: entiendes el **loop del agente**, cuándo conviene un **equipo de subagentes**, cómo **Cowork** ejecuta proyectos de oficina completos y cómo las **tareas programadas** eliminan lo repetitivo. Para muchísimos proyectos, hasta aquí es todo lo que necesitas. El Nivel 4 es para quienes quieren construir el sistema con sus propias manos.

---
---
