# Módulo 7 · Evals, seguridad y control humano

**Duración:** 5 horas.

## Objetivos

- Diseñar evaluaciones reproducibles.
- Aplicar controles según nivel de riesgo.
- Implementar puertas humanas.
- Preparar el sistema para fallos previsibles.

## Principio general

Un agente no es confiable porque una demostración salió bien. Es confiable cuando pasa pruebas repetibles, falla de forma segura y deja evidencia suficiente para investigar.

## Set dorado

Crear entre 30 y 50 casos que incluyan:

- casos normales;
- información faltante;
- solicitudes ambiguas;
- manipulación del usuario;
- herramienta caída;
- datos obsoletos;
- contradicciones;
- acciones fuera de alcance;
- límites de costo;
- ciclos que no terminan.

## Métricas

- precisión de respuesta;
- selección correcta de herramienta;
- parámetros correctos;
- tasa de escalamiento correcto;
- alucinaciones;
- cumplimiento de políticas;
- costo por caso;
- latencia;
- porcentaje de casos que requieren intervención.

## Controles por riesgo

| Acción | Riesgo | Control |
|---|---|---|
| consultar información | bajo | autónomo con log |
| preparar un borrador | bajo | autónomo |
| enviar recordatorio | medio | muestreo o aprobación según contexto |
| cambiar precio o condición | alto | aprobación obligatoria |
| comprometer dinero | alto | aprobación obligatoria |
| pagar, dar crédito o borrar | crítico | el agente prepara; una persona ejecuta |

## Defensa en profundidad

Los límites críticos no deben depender solo del prompt.

Capas:

1. instrucciones;
2. validación de entrada;
3. permisos de herramientas;
4. reglas en código;
5. aprobación humana;
6. logs y alertas;
7. reversión.

## Seguridad de datos

Documentar:

- clasificación de datos;
- acceso mínimo necesario;
- secretos y claves;
- separación entre clientes;
- retención de logs;
- datos personales;
- prevención de prompt injection;
- fuentes externas no confiables.

## FerreAgente

Simulacros:

- cliente insiste por descuento;
- producto inexistente;
- inventario no responde;
- proveedor envía un precio absurdo;
- orden supera presupuesto;
- recomendación contradice política;
- prompt externo intenta cambiar instrucciones.

## Construcción

```text
evals/casos-dorados.jsonl
evals/criterios.md
evals/reporte.md
aprobaciones/cola.*
configuracion/matriz-riesgos.md
configuracion/politica-datos.md
```

## Entregable

Suite de pruebas con resultados reportados, matriz de riesgos y demostración de que una acción de alto riesgo no puede ejecutarse sin aprobación.