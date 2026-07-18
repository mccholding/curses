# Módulo 6 · Multimodalidad, verificación y debugging

**Duración:** 60 minutos.

## Objetivos

- Elegir entre texto, voz, imagen y archivos según la tarea.
- Utilizar multimodalidad para aportar contexto, no para perder control.
- Verificar hechos, cálculos, fuentes y cumplimiento.
- Corregir resultados mediante un proceso de debugging.

## Elegir el canal

| Canal | Mejor para | Riesgo |
|---|---|---|
| Texto | precisión, plantillas, formatos y restricciones | omitir contexto por escribir poco |
| Voz | explicar rápidamente una situación compleja | instrucciones desordenadas o ambiguas |
| Imagen | interfaces, diagramas, errores visuales, evidencia | asumir detalles que no son visibles |
| Archivo | reportes, políticas, datos y documentos extensos | usar versiones obsoletas o fuentes irrelevantes |

## Flujo recomendado con voz

```text
Voy a explicarte el contexto por voz. No produzcas el entregable todavía.
Cuando diga “FIN”:
1. resume el contexto en bullets;
2. separa hechos, opiniones y supuestos;
3. hazme las preguntas necesarias;
4. propón una instrucción estructurada para confirmar.
```

## Imágenes como contexto

Al adjuntar una imagen, definir:

- qué debe observar;
- qué decisión apoyará;
- qué elementos son importantes;
- qué no puede inferir;
- cómo debe reportar incertidumbre.

Ejemplo:

```text
Analiza esta captura del proceso de pago.
Identifica problemas visibles de claridad y jerarquía.
No asumas datos de conversión ni comportamiento que la imagen no demuestra.
Entrega: hallazgo, evidencia visual, impacto probable y recomendación.
```

## Protocolo de verificación

1. Separar hechos, inferencias y recomendaciones.
2. Revisar que cada cifra provenga de una fuente identificada.
3. Comprobar cálculos con los datos originales.
4. Comparar la salida contra los criterios de aceptación.
5. Identificar información faltante.
6. Declarar incertidumbre.
7. Reservar revisión humana para decisiones sensibles.

## Debugging de respuestas

Cuando el resultado falla, no comenzar desde cero inmediatamente.

```text
1. Describe el fallo observable.
2. Identifica qué criterio no cumplió.
3. Localiza la causa probable: instrucción, contexto, fuente, formato o verificación.
4. Corrige solo la causa relevante.
5. Regenera o modifica la parte afectada.
6. Vuelve a verificar.
```

## Árbol rápido

- **Genérico:** falta objetivo, audiencia o evidencia.
- **Demasiado largo:** falta límite o estructura.
- **Inventado:** faltan fuentes y regla de incertidumbre.
- **Formato incorrecto:** el formato no era verificable.
- **Mezcla información:** el contexto contiene fuentes o conversaciones incompatibles.
- **No termina:** el loop no tiene condición de parada.

## Práctica guiada

Resolver una tarea combinando dos canales, por ejemplo:

- voz + texto;
- imagen + instrucciones;
- PDF + tabla de evidencia;
- CSV + reporte ejecutivo.

Después, introducir deliberadamente un error y aplicar el protocolo de debugging.

## Entregable

Flujo multimodal con:

- selección justificada de canales;
- instrucción estructurada;
- evidencia utilizada;
- verificación;
- registro de una corrección.