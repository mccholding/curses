# Plantilla Prompt–Context–Loop

## 1. Prompt

```markdown
# Objetivo
[resultado observable]

# Audiencia
[quién usará o recibirá el resultado]

# Información de entrada
[datos, archivos, texto o situación]

# Tarea
1. [acción]
2. [acción]
3. [acción]

# Formato
[estructura, longitud, idioma y tono]

# Restricciones
- No [acción o contenido prohibido].
- Si falta [dato crítico], pregunta antes de continuar.
- No inventes cifras, fuentes, citas o políticas.

# Criterios de aceptación
- Debe incluir [elemento].
- Debe permitir [uso].
- Debe evitar [fallo].
```

## 2. Contexto

```markdown
# Propósito del espacio
[para qué existe]

# Información permanente
[audiencia, organización, producto, tono, reglas]

# Fuentes de verdad
- [fuente + fecha o versión]

# Referencias
- [ejemplos, plantillas o reportes anteriores]

# Información temporal
- [datos del periodo o tarea]

# Decisiones tomadas
- [decisiones que no deben reabrirse]

# Contenido excluido
- [duplicados, versiones obsoletas, información sensible]

# Regla de actualización
[cuándo y quién revisa el contexto]

# Criterio de suficiencia
La IA tiene contexto suficiente cuando puede [resultado]
sin que yo repita [información estable].
```

## 3. Loop

```markdown
# Objetivo del ciclo
[resultado final]

# Entradas
[datos, documentos, herramientas]

# Pasos
1. Validar entradas.
2. Ejecutar la tarea.
3. Verificar el resultado.
4. Diagnosticar incumplimientos.
5. Corregir la parte afectada.
6. Volver a verificar.

# Verificador
[reglas, checklist, fuente o cálculo]

# Condición de éxito
[criterios que deben cumplirse]

# Condiciones de parada
- éxito;
- falta de información crítica;
- riesgo no autorizado;
- máximo de [número] intentos;
- tiempo o costo máximo.

# Checkpoint humano
Pedir aprobación antes de [enviar, publicar, gastar, eliminar o decidir].

# Registro
Guardar [decisiones, errores, cambios y resultado].
```

## 4. Prueba

- Caso normal.
- Caso con información faltante.
- Caso con fuente contradictoria.
- Caso que debe activar el checkpoint humano.
- Caso que debe detenerse por límite.

## 5. Revisión final

- ¿El prompt define un resultado?
- ¿El contexto contiene solo información relevante y vigente?
- ¿El loop puede verificar su propio resultado?
- ¿Existen límites claros?
- ¿Las acciones sensibles conservan control humano?
- ¿Otra persona podría reutilizar el sistema?