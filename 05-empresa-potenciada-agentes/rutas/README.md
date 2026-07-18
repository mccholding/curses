# Rutas de implementación

## Estándar común

Las dos rutas deben producir los mismos resultados funcionales:

- agentes con contratos claros;
- herramientas con permisos;
- datos documentados;
- pruebas de aceptación;
- evals;
- aprobación humana;
- logs;
- cálculo de costos;
- manual operativo.

La ruta low-code no es una versión de menor calidad. Cambia el medio de implementación.

## Ruta A · Low-code

### Perfil

Profesionales, operadores, consultores y dueños de negocio sin experiencia de programación.

### Stack orientativo

- n8n o Make;
- Google Sheets, Airtable o base integrada;
- proveedor de modelos;
- conectores nativos o MCP cuando esté disponible;
- correo, mensajería o formularios.

### Evidencias

- exportación del workflow;
- capturas de nodos y permisos;
- datos de prueba;
- historial de ejecuciones;
- reporte de evals;
- procedimiento de pausa y recuperación.

## Ruta B · Python

### Perfil

Desarrolladores, automatizadores y participantes con fundamentos de programación.

### Stack orientativo

- Python;
- SDK del proveedor de modelos;
- SQLite o PostgreSQL;
- MCP cuando aporte reutilización;
- framework agéntico después de construir un loop manual;
- Git y GitHub;
- herramienta de observabilidad.

### Evidencias

- código ejecutable;
- archivo de dependencias;
- `.env.example` sin secretos;
- pruebas automatizadas;
- evals;
- logs;
- documentación de despliegue.

## Regla sobre frameworks

No introducir un framework multiagente antes de comprender:

1. el ciclo de herramientas;
2. el estado;
3. el enrutamiento;
4. la verificación;
5. los límites;
6. la observabilidad.

El framework debe resolver una necesidad reconocida, no sustituir la comprensión.

## Equivalencias

| Capacidad | Low-code | Python |
|---|---|---|
| entrada | formulario, webhook o chat | endpoint, CLI o interfaz |
| agente | nodo de IA | SDK o framework |
| herramienta | nodo o subworkflow | función o servicio |
| datos | hoja o base no-code | SQLite/PostgreSQL |
| coordinación | subworkflows y condiciones | código o grafo |
| aprobación | formulario o cola | interfaz o estado pendiente |
| observabilidad | historial de plataforma | logs, trazas y dashboard |

## Selección

Elegir la ruta según:

- capacidad de mantenimiento;
- necesidad de personalización;
- sensibilidad de datos;
- presupuesto;
- volumen;
- velocidad del piloto;
- equipo disponible.

Se permite cambiar de ruta después del Módulo 2, siempre que el alumno documente el motivo.