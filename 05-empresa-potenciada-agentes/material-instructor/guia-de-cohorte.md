# Guía de cohorte

## Antes de comenzar

El instructor debe:

- verificar que las herramientas y SDK utilizados siguen vigentes;
- ejecutar el caso FerreAgente de principio a fin;
- revisar precios y límites de los proveedores;
- preparar datos simulados;
- comprobar que no existen secretos en el repositorio;
- actualizar los casos empresariales y sus fuentes;
- definir una ruta low-code y una ruta Python soportadas durante la cohorte.

## Diagnóstico de entrada

Comprobar que el participante puede:

- estructurar una instrucción;
- distinguir contexto permanente y temporal;
- explicar agente, herramienta y workflow;
- manejar archivos y tablas;
- describir un proceso real;
- cumplir los prerrequisitos de su ruta.

Quienes no cumplen deben completar material puente de los cursos 01 y 02.

## Ritmo semanal

1. revisión del componente anterior;
2. demostración del principio general;
3. implementación en FerreAgente;
4. transferencia por sectores;
5. construcción individual;
6. prueba de fallo;
7. commit y documentación.

Al menos 60 % del tiempo debe dedicarse a construcción y pruebas.

## Control de alcance

Señales de un proyecto demasiado amplio:

- más de cinco agentes antes del Módulo 5;
- múltiples canales externos desde el inicio;
- datos reales sensibles sin entorno de prueba;
- pagos o acciones irreversibles como primera automatización;
- intención de construir un ERP completo;
- ausencia de un resultado observable.

Reducir alcance antes de continuar.

## Revisiones obligatorias

### Semana 2

Primer agente, fuente de datos y pruebas.

### Semana 5

Arquitectura multiagente y comparación con workflow.

### Semana 7

Evals, permisos y acciones sensibles.

### Semana 8

Operación, costos y recuperación.

### Semana 10

Demo, documentación y retrospectiva.

## Uso responsable de ejemplos

No presentar cifras excepcionales de empresas unipersonales como resultados típicos. Utilizar casos para discutir posibilidades, decisiones arquitectónicas y límites.

## Política sobre herramientas

La arquitectura es más importante que una marca. Cuando cambie un SDK, framework o modelo:

- actualizar la implementación;
- conservar el principio;
- registrar fecha de revisión;
- añadir una prueba de regresión;
- evitar enseñar interfaces obsoletas como si fueran permanentes.

## Evidencia del aprendizaje

El instructor debe evaluar el proceso, no solamente el video final:

- historial de versiones;
- changelog;
- casos de prueba;
- fallos encontrados;
- decisiones descartadas;
- costo medido;
- controles añadidos.