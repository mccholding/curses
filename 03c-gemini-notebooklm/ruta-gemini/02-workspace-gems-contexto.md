# Módulos 2–3 · Google Workspace, contexto y Gems

**Duración:** 4 horas.

## Objetivos

- Diseñar un flujo que use información autorizada de Google Workspace.
- Distinguir datos personales, compartidos y empresariales.
- Construir una Gem con instrucciones, límites y pruebas.
- Aplicar Context Engineering sin sobrecargar el sistema.

## Workspace como fuente de trabajo

El alumno identifica qué información vive en:

- Gmail;
- Drive;
- Docs;
- Sheets;
- Slides;
- Calendar;
- archivos locales;
- fuentes externas.

No se enseña a “dar acceso a todo”. Se aplica permiso mínimo: solo las cuentas, carpetas, archivos o servicios necesarios para el objetivo.

## Casos prácticos

- preparar una reunión desde correos, calendario y documentos;
- localizar decisiones dispersas en Drive;
- resumir el estado de un proyecto;
- transformar datos de una hoja en un briefing;
- preparar una presentación desde fuentes aprobadas.

## Anatomía de una Gem

```text
ROL
OBJETIVO
USUARIOS
CONTEXTO AUTORIZADO
PROCESO
FORMATO
RESTRICCIONES
CRITERIOS DE CALIDAD
ESCALAMIENTO
CASOS DE PRUEBA
```

## Pruebas obligatorias

La Gem debe probarse con:

1. caso normal;
2. información faltante;
3. solicitud fuera de alcance;
4. intento de cambiar una política;
5. fuente contradictoria;
6. dato sensible;
7. formato incorrecto;
8. instrucción ambigua;
9. caso límite;
10. solicitud que requiere aprobación humana.

## Entregables

- mapa de fuentes y permisos;
- Gem especializada;
- diez pruebas con resultado esperado;
- changelog de correcciones;
- política de actualización del contexto.
