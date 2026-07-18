# Pack de plantillas

## 1. Perfil de empresa

```markdown
# Empresa o proyecto
## Problema que resuelve
## Usuarios y clientes
## Procesos principales
## Sistemas y fuentes actuales
## Restricciones
## Datos sensibles
## Responsable humano
```

## 2. Mapa de procesos

| Proceso | Frecuencia | Dolor | Variabilidad | Datos | Verificable | Riesgo | Solución mínima |
|---|---:|---:|---:|---:|---:|---:|---|

## 3. Ficha de agente

```markdown
# Nombre
## Objetivo observable
## Usuarios
## Entradas
## Fuentes de verdad
## Herramientas
## Políticas
## Acciones prohibidas
## Salida
## Verificación
## Escalamiento
## Condición de parada
## Límites
## Responsable
```

## 4. Ficha de herramienta

```markdown
# Herramienta
## Acción única
## Cuándo usar
## Cuándo no usar
## Parámetros
## Salida
## Errores útiles
## Tipo: lectura / propuesta / escritura
## Permisos
## Reversibilidad
## Log requerido
```

## 5. Matriz de riesgos

| Acción | Datos | Impacto | Probabilidad | Nivel | Control técnico | Aprobación | Recuperación |
|---|---|---:|---:|---|---|---|---|

## 6. Caso de evaluación

```json
{
  "id": "CASO-001",
  "categoria": "normal|limite|adversarial|fallo",
  "entrada": "",
  "estado_inicial": {},
  "herramientas_esperadas": [],
  "acciones_prohibidas": [],
  "criterios": [],
  "debe_escalar": false,
  "notas": ""
}
```

## 7. Rutina programada

```markdown
# Rutina
## Propósito
## Horario y zona
## Fuentes
## Pasos
## Verificación
## Presupuesto
## Condición de no ejecución
## Aprobaciones
## Entrega
## Responsable
## Procedimiento de pausa
```

## 8. Incidente

```markdown
# Incidente
## Fecha y ejecución
## Qué ocurrió
## Impacto
## Datos afectados
## Acción inmediata
## Causa
## Recuperación
## Cambio preventivo
## Eval añadido
```

## 9. ROI

| Concepto | Antes | Después | Evidencia |
|---|---:|---:|---|
| minutos por caso | | | |
| casos por mes | | | |
| costo humano | | | |
| costo de modelos | | | |
| software | | | |
| revisión humana | | | |
| errores y retrabajo | | | |
| valor generado o protegido | | | |

## 10. Decisión de arquitectura

```markdown
# Decisión
## Contexto
## Alternativas
## Opción elegida
## Por qué
## Riesgos
## Cómo se probará
## Cuándo se revisará
```