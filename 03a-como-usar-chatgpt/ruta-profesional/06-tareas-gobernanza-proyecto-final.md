# Bloque 6 · Tareas programadas, gobernanza y proyecto final

Este archivo reúne los módulos 8 y 9 de la Ruta profesional.

---

# Módulo 8 · Tareas programadas y monitoreo

**Duración:** 90 minutos.

## Objetivos

- Diseñar tareas únicas, recurrentes y de monitoreo.
- Elegir una frecuencia razonable.
- Definir cuándo notificar y cuándo guardar silencio.
- Conectar tareas con Projects, apps y Work cuando estén disponibles.

## 8.1 Tipos de tarea

| Tipo | Ejemplo | Resultado esperado |
|---|---|---|
| Única | recordar una fecha | notificación puntual |
| Recurrente | resumen diario | entrega en cada ejecución |
| Monitoreo | avisar cuando cambie una condición | notificación solo si existe novedad relevante |
| Trabajo programado | producir un informe semanal | entregable terminado con fuentes |

## 8.2 Anatomía

```markdown
# Objetivo
[qué debe conseguir cada ejecución]

# Fuentes
[web, Project, apps o archivos]

# Frecuencia
[hora, día o ventana]

# Criterio de relevancia
[qué merece una notificación]

# Formato
[estructura del resultado]

# Memoria entre ejecuciones
[qué debe comparar con resultados anteriores]

# Condición final
[cuándo puede detenerse]

# Límites
[frecuencia, alcance, costos, acciones]
```

## 8.3 Diseñar buen monitoreo

Una tarea de monitoreo debe:

- recordar qué encontró antes;
- evitar duplicados;
- distinguir cambio material de ruido;
- declarar fuente y fecha;
- notificar solo cuando el criterio se cumple;
- detenerse cuando alcanza la condición final;
- permitir pausa, edición o eliminación.

## 8.4 Frecuencia

No se debe usar una frecuencia alta por defecto.

Preguntas:

- ¿con qué rapidez puede cambiar la condición?
- ¿qué daño produce enterarse más tarde?
- ¿cuánto ruido generará?
- ¿qué límites tiene el plan?
- ¿hay otra fuente o evento más apropiado?

## 8.5 Tareas y apps

Cuando una tarea usa apps:

- confirmar que la conexión estará disponible;
- documentar permisos persistentes;
- evitar acciones irreversibles sin aprobación;
- prever qué ocurre si la autenticación vence;
- revisar límites del espacio de trabajo;
- no depender de webhooks cuando la capacidad no existe.

## 8.6 Errores comunes

- crear un recordatorio cuando se necesita monitoreo;
- notificar aunque no haya cambios;
- no comparar contra ejecuciones anteriores;
- solicitar una frecuencia no compatible;
- conectar demasiadas fuentes;
- no definir fecha, zona horaria o ventana;
- programar una tarea sin criterio de finalización.

## Práctica guiada

Configurar una tarea real:

- resumen de mercado;
- seguimiento de un proyecto;
- preparación de reunión;
- monitoreo de regulación;
- revisión semanal de métricas;
- alerta sobre una condición.

## Entregable

Tarea activa o especificación completa con calendario, fuentes, criterio de relevancia, ejemplo de notificación y condición de silencio.

---

# Módulo 9 · Gobernanza y proyecto final

**Duración:** 90 minutos.

## Objetivos

- Administrar datos, memoria, permisos y acciones.
- Documentar responsables y controles.
- Integrar todas las capacidades en un sistema de trabajo.
- Presentar evidencia de utilidad y confiabilidad.

## 9.1 Cuatro preguntas de gobernanza

1. ¿Qué información puede consultar?
2. ¿Qué acciones puede ejecutar?
3. ¿Qué debe aprobar una persona?
4. ¿Quién responde cuando falla?

## 9.2 Clasificación de riesgo

| Nivel | Ejemplo | Control |
|---|---|---|
| Bajo | resumir o buscar información pública | revisión básica |
| Medio | producir un borrador o análisis interno | revisión antes de usar |
| Alto | enviar, publicar o modificar datos | aprobación humana obligatoria |
| Crítico | pagos, decisiones legales, médicas o laborales | preparar, nunca ejecutar autónomamente |

## 9.3 Privacidad y datos

El estudiante debe revisar:

- controles de datos;
- uso de conversaciones para mejora de modelos;
- memoria;
- Chat temporal;
- archivos cargados;
- apps conectadas;
- destinatarios externos;
- permisos del espacio de trabajo;
- retención y eliminación;
- información que nunca debe compartirse.

## 9.4 Registro del sistema

```markdown
# Nombre del sistema

## Propósito

## Responsable

## Usuarios

## Project y fuentes

## GPTs o configuraciones

## Plugins y apps

## Tareas programadas

## Datos sensibles

## Acciones permitidas

## Acciones prohibidas

## Aprobaciones

## Casos de prueba

## Fallos conocidos

## Fecha de última revisión
```

## 9.5 Proyecto final

Construir un sistema profesional con:

- un Project bien organizado;
- instrucciones persistentes;
- fuentes clasificadas;
- investigación con citas;
- un entregable en Canvas o Work;
- un GPT probado;
- una conexión o diseño de conexión;
- una tarea programada;
- controles de privacidad y permisos;
- manual de continuidad.

## 9.6 Pruebas obligatorias

1. caso normal;
2. dato faltante;
3. fuente contradictoria;
4. solicitud fuera de alcance;
5. intento de cambiar una regla;
6. app o fuente no disponible;
7. acción que requiere aprobación;
8. resultado con cita incorrecta;
9. tarea sin cambio material;
10. traspaso a una nueva conversación o persona.

## 9.7 Presentación

La demostración debe mostrar:

- problema inicial;
- arquitectura;
- evidencia de funcionamiento;
- errores encontrados;
- controles;
- tiempo o calidad mejorados;
- límites;
- siguiente versión.

## Entregable

Sistema de trabajo funcional, manual operativo, matriz de riesgos, resultados de pruebas y demostración de diez minutos.