# Bloque 5 · GPTs, plugins y apps

Este archivo reúne los módulos 6 y 7 de la Ruta profesional.

---

# Módulo 6 · GPTs personalizados

**Duración:** 2 horas.

## Objetivos

- Diseñar un GPT para un proceso específico.
- Separar instrucciones, conocimiento, capacidades y conexiones.
- Probar comportamiento normal, límites y errores.
- Decidir cuándo un GPT aporta valor frente a un Project.

## 6.1 Cuándo crear un GPT

Un GPT tiene sentido cuando:

- varias personas necesitan la misma experiencia;
- existe un método estable;
- deben reutilizarse instrucciones y conocimiento;
- conviene ofrecer iniciadores de conversación;
- se necesita controlar capacidades disponibles;
- el proceso se repetirá en chats nuevos.

No es la mejor opción cuando el trabajo depende de un historial de proyecto en evolución o de datos de un cliente que no deben mezclarse.

## 6.2 Anatomía

```text
Nombre y descripción
Usuarios
Problema que resuelve
Instrucciones
Conocimiento
Capacidades
Plugins o apps / Acciones
Iniciadores de conversación
Límites
Escalamiento
Casos de prueba
Historial de versiones
```

## 6.3 Instrucciones

Las instrucciones deben definir:

- rol;
- objetivo;
- proceso;
- fuentes prioritarias;
- criterios de calidad;
- formato;
- límites;
- cuándo preguntar;
- cuándo detenerse;
- cuándo escalar.

Evitar instrucciones que dependan de nombres de botones o modelos temporales.

## 6.4 Conocimiento

Los archivos deben:

- ser relevantes;
- tener fecha y propietario;
- distinguir política vigente de ejemplo;
- evitar duplicados;
- eliminar datos sensibles innecesarios;
- incluir una regla de actualización.

El conocimiento no sustituye una conexión a datos que cambian con frecuencia.

## 6.5 Capacidades y conexiones

Un GPT puede utilizar capacidades de ChatGPT y conectarse con servicios externos. Antes de habilitarlos, documentar:

- qué datos salen del entorno;
- quién administra la conexión;
- qué acciones puede realizar;
- qué requiere aprobación;
- cómo se revoca el acceso.

Un GPT debe diseñarse con apps o con acciones según la arquitectura disponible, evitando duplicar conexiones sin necesidad.

## 6.6 Pruebas de aceptación

El set mínimo incluye:

1. solicitud normal;
2. información faltante;
3. petición fuera de alcance;
4. fuente contradictoria;
5. intento de cambiar políticas;
6. dato no presente;
7. acción de alto riesgo;
8. formato obligatorio;
9. usuario que insiste;
10. respuesta que requiere cita o verificación.

## 6.7 Publicación

Antes de compartir:

- revisar instrucciones y archivos;
- retirar secretos;
- probar enlaces o conexiones;
- definir audiencia;
- comprobar permisos del espacio de trabajo;
- documentar responsable y fecha de revisión;
- preparar canal para reportar fallos.

## Práctica guiada

Construir un GPT para uno de estos procesos:

- preparación de propuestas;
- tutor de capacitación;
- revisión de documentos;
- asistente de reuniones;
- generador de briefs;
- guía de políticas internas.

## Entregable

GPT funcional más ficha de arquitectura, inventario de conocimiento, diez casos de prueba y registro de versión.

---

# Módulo 7 · Plugins y apps

**Duración:** 2 horas.

## Objetivos

- Entender la relación entre plugins, apps, skills y plantillas.
- Conectar información externa sin copiar todo al chat.
- Aplicar permisos mínimos y aprobación humana.
- Distinguir búsqueda, sincronización y acción.

## 7.1 Conceptos

- **Plugin:** paquete que habilita un flujo y puede incluir skills, apps o plantillas.
- **App:** integración con información o acciones externas.
- **Sincronización:** indexación anticipada de fuentes seleccionadas.
- **Acción:** operación que modifica o envía información.
- **MCP:** protocolo que puede utilizarse para construir apps personalizadas y exponer herramientas aprobadas.

Los nombres comerciales pueden cambiar. La arquitectura central permanece: contexto, herramienta, permiso, acción y registro.

## 7.2 Cuatro capacidades

| Capacidad | Ejemplo | Riesgo |
|---|---|---|
| Buscar | localizar un documento | traer contenido incorrecto o no autorizado |
| Consultar | responder usando datos conectados | mezclar fuentes o permisos |
| Sincronizar | preparar conocimiento para recuperación | indexar información obsoleta o excesiva |
| Actuar | crear, actualizar, enviar o modificar | ejecutar una acción equivocada |

## 7.3 Matriz de permisos

| Recurso | Leer | Crear | Editar | Eliminar | Aprobación |
|---|---:|---:|---:|---:|---|

Aplicar el principio de menor privilegio: habilitar únicamente lo necesario para el proceso.

## 7.4 Flujo seguro

```text
Solicitud
→ identificar app o plugin
→ comprobar permisos
→ recuperar contexto
→ proponer acción
→ mostrar resumen
→ solicitar aprobación cuando corresponda
→ ejecutar
→ registrar resultado
```

## 7.5 Datos conectados

Antes de conectar una fuente:

- definir propietario;
- clasificar sensibilidad;
- establecer qué carpetas o elementos entran;
- excluir información innecesaria;
- decidir frecuencia de actualización;
- comprobar cómo se desconecta;
- verificar políticas del espacio de trabajo.

## 7.6 Acciones de alto riesgo

Requieren control humano:

- enviar comunicaciones externas;
- cambiar registros;
- eliminar información;
- comprometer recursos;
- aceptar términos;
- publicar;
- modificar permisos;
- tomar decisiones laborales, financieras, médicas o legales.

## 7.7 Errores comunes

- conectar toda la cuenta cuando basta una carpeta;
- confundir autorización con exactitud;
- no revisar la fuente recuperada;
- habilitar escritura para un proceso de lectura;
- dejar conexiones sin propietario;
- no probar qué ocurre cuando la app falla;
- asumir que una sincronización está siempre actualizada.

## Práctica guiada

Diseñar un flujo conectado con:

- una fuente externa;
- una consulta de lectura;
- una acción opcional;
- permisos definidos;
- aprobación;
- registro;
- plan alternativo si la app no está disponible.

## Entregable

Diagrama del flujo conectado, matriz de permisos, prueba normal, prueba de fallo y protocolo de desconexión.