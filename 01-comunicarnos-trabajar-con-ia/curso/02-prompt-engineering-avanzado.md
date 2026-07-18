# Módulo 2 · Prompt Engineering avanzado

**Duración:** 75 minutos.

## Objetivos

- Convertir prompts útiles en plantillas reutilizables.
- Iterar con feedback específico.
- Separar hechos, supuestos e inferencias.
- Diseñar criterios de aceptación antes de generar el resultado.

## De prompt a plantilla

Una plantilla conserva la estructura y cambia únicamente las variables.

```markdown
# Objetivo
Crear [entregable] para lograr [resultado].

# Audiencia
[quién lo utilizará o recibirá]

# Información disponible
[datos, texto, archivos o decisiones]

# Instrucciones
1. [acción]
2. [acción]
3. [acción]

# Formato
[estructura, extensión, tono]

# Restricciones
- No [acción prohibida].
- Si falta [dato crítico], pregunta antes de continuar.
- No inventes cifras, fuentes ni políticas.

# Criterios de aceptación
- Debe incluir [elemento].
- Debe poder utilizarse para [situación].
- Debe evitar [fallo].
```

## El segundo mensaje

La interacción profesional no consiste en aceptar el primer resultado. Consiste en dirigir la mejora.

Feedback débil:

```text
No me gusta.
```

Feedback útil:

```text
Conserva la estructura, pero reduce el texto un 30 %, cambia el tono a ejecutivo y convierte las recomendaciones en acciones con responsable y fecha.
```

## Patrones de iteración

- **Reducir:** “Hazlo 30 % más corto sin perder decisiones ni cifras”.
- **Precisar:** “Reemplaza recomendaciones genéricas por acciones observables”.
- **Comparar:** “Genera tres opciones y explica el criterio de cada una”.
- **Cuestionar:** “Identifica los supuestos débiles antes de recomendar”.
- **Completar:** “Hazme hasta cinco preguntas antes de comenzar”.
- **Verificar:** “Compara el resultado contra los criterios y corrige incumplimientos”.

## Roles: uso correcto

Un rol puede aportar perspectiva, pero no sustituye datos ni fuentes.

Mejor que:

```text
Actúa como experto en marketing.
```

Usar:

```text
Evalúa esta campaña desde la perspectiva de una directora de marketing B2B responsable de generación de demanda. Prioriza claridad de propuesta, calidad del lead y posibilidad de medición. No inventes benchmarks.
```

## Fórmulas del material anterior

Las fórmulas como PROMPT, TEACH, CRAFT, MAPS, DEBUG, APRENDE, TRAZA, RUMBO y ARREGLA pueden mantenerse como ayudas de memoria. Deben enseñarse como checklists flexibles, no como palabras mágicas.

## Práctica guiada

1. Convertir un prompt exitoso en plantilla.
2. Probarlo con dos casos distintos.
3. Detectar qué partes son permanentes y cuáles variables.
4. Aplicar dos ciclos de feedback específico.
5. Comparar la primera respuesta con la versión final.

## Entregable

Una plantilla reutilizable con:

- variables identificadas;
- criterios de aceptación;
- tres instrucciones de iteración;
- una regla de incertidumbre;
- evidencia de uso en dos casos.

## Evaluación rápida CLEAR

- **Correcto:** cumple la tarea.
- **Lógico:** mantiene coherencia.
- **Exacto:** evita ambigüedad y datos inventados.
- **Accionable:** puede utilizarse.
- **Repetible:** funciona más de una vez.