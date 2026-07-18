# Bloque 3 · Conectores, delegación y automatización

Este archivo reúne los módulos 5 y 6 de la Ruta profesional.

---

# Módulo 5 · Conectores y MCP para profesionales

**Duración:** 2 horas.

## Objetivos

- Comprender qué cambia cuando Claude accede a herramientas reales.
- Elegir conectores según una necesidad concreta.
- Aplicar permisos mínimos y pruebas de bajo riesgo.
- Diseñar un flujo conectado con trazabilidad y aprobación.

## Contenido

### 5.1 Del copiar y pegar al flujo conectado

Sin conexión, el usuario transporta información manualmente. Con un conector, Claude puede consultar fuentes o realizar acciones según los permisos disponibles.

La pregunta correcta no es “¿qué puedo conectar?”, sino:

> ¿Qué fricción real desaparece con esta conexión y qué riesgo nuevo aparece?

### 5.2 Lectura y escritura

Distinguir siempre:

- **Consultar:** leer correos, archivos, eventos o registros.
- **Preparar:** redactar una respuesta, propuesta o cambio sin ejecutarlo.
- **Actuar:** enviar, agendar, modificar, publicar o borrar.

La progresión recomendada es:

```text
Solo lectura → propuesta de acción → aprobación humana → ejecución limitada
```

### 5.3 Matriz de permisos

| Acción | Riesgo | Control recomendado |
|---|---|---|
| Leer agenda | Bajo | Acceso limitado a calendario necesario |
| Leer archivos internos | Medio | Carpetas específicas y clasificación de datos |
| Crear un borrador | Medio | Revisión antes de enviar |
| Modificar registros | Alto | Confirmación y registro de cambios |
| Enviar, publicar, borrar o pagar | Muy alto | Aprobación humana obligatoria |

### 5.4 Diseño de un flujo conectado

Documentar:

1. Disparador o petición.
2. Fuente que Claude consulta.
3. Datos mínimos necesarios.
4. Transformación o análisis.
5. Entregable o acción propuesta.
6. Punto de aprobación.
7. Registro de lo realizado.

## Práctica guiada

Conectar una herramienta de bajo riesgo y ejecutar un flujo de solo lectura, por ejemplo:

- resumir agenda y preparar reuniones;
- localizar archivos relacionados con un proyecto;
- identificar mensajes pendientes sin responderlos;
- consolidar actualizaciones de una herramienta de gestión.

## Entregable

Diagrama del flujo, tabla de permisos y evidencia de una ejecución supervisada.

---

# Módulo 6 · Delegación, agentes y tareas repetitivas

**Duración:** 2 horas.

## Objetivos

- Convertir una secuencia de preguntas en una delegación completa.
- Definir objetivo, criterio de terminado y límites.
- Reconocer cuándo dividir una tarea entre especialistas.
- Automatizar únicamente procesos que ya funcionan de forma supervisada.

## Contenido

### 6.1 De instrucción a delegación

Una delegación completa contiene:

```text
Objetivo
Contexto y fuentes
Entregable
Criterios de calidad
Herramientas permitidas
Acciones prohibidas
Checkpoint humano
Condición de terminado
```

Ejemplo:

```text
Prepara el informe semanal de operaciones usando los archivos del Project
y las actualizaciones del gestor de tareas conectado.

El informe debe incluir: estado general, bloqueos, decisiones necesarias,
responsables y fechas. Contrasta cada estado con su fuente.

No envíes el informe. Déjalo como borrador y detente para mi aprobación.
Está terminado cuando todos los proyectos activos aparecen y cada bloqueo
tiene responsable o está marcado como “sin asignar”.
```

### 6.2 Loop de trabajo

```text
Observar → planear → actuar → verificar → corregir → entregar
```

El instructor debe mostrar que delegar no significa abandonar la responsabilidad. El humano define el resultado, los límites y la revisión.

### 6.3 Especialistas y revisión separada

Dividir cuando hay funciones distintas:

- investigador;
- analista;
- redactor;
- revisor de datos;
- revisor de cumplimiento.

La persona o agente que verifica debe usar criterios independientes del que produjo el trabajo.

### 6.4 Automatización gradual

```text
Fase 1 · Manual asistida
Fase 2 · Delegada y revisada en cada ejecución
Fase 3 · Programada con revisión frecuente
Fase 4 · Programada con revisión por excepción
```

No se programa una tarea que todavía falla de forma manual.

### 6.5 Condiciones para automatizar

La tarea debe tener:

- entradas consistentes;
- pasos suficientemente estables;
- verificación medible;
- manejo de errores;
- límite de intentos;
- responsable humano;
- registro de ejecuciones.

## Práctica guiada

Tomar el proceso transversal del curso y redactar una delegación completa. Ejecutarla una vez, revisar el resultado y ajustar sus criterios.

## Entregable

Ficha de delegación con:

- objetivo;
- criterio de terminado;
- roles;
- permisos;
- verificación;
- checkpoint humano;
- frecuencia potencial;
- plan de adopción gradual.

## Evaluación rápida

El flujo no aprueba si usa expresiones vagas como “que quede bien”, “hazlo profesional” o “revísalo todo” sin criterios observables.
