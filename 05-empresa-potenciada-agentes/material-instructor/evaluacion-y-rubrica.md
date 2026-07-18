# Evaluación y rúbrica

## Componentes

| Componente | Peso |
|---|---:|
| Definición del problema y arquitectura | 15 % |
| Agentes, herramientas y coordinación | 25 % |
| Datos y context engineering | 10 % |
| Evals, seguridad y control humano | 20 % |
| Producción, observabilidad y operación | 15 % |
| Economía, documentación y presentación | 15 % |

## 1. Problema y arquitectura · 15 puntos

- El proceso es real y está claramente delimitado.
- Se consideró una alternativa más simple.
- Los agentes tienen responsabilidades distintas.
- El nivel de autonomía está justificado.
- Existen decisiones explícitamente reservadas a una persona.

## 2. Agentes, herramientas y coordinación · 25 puntos

- Contratos operativos claros.
- Herramientas pequeñas y bien descritas.
- Uso correcto de fuentes.
- Patrón de coordinación adecuado.
- Manejo de errores y resultados contradictorios.
- Condiciones de parada y límites.

## 3. Datos y contexto · 10 puntos

- Fuentes de verdad identificadas.
- Información vigente y relevante.
- Permisos documentados.
- Separación entre contexto estable y temporal.
- Duplicados y versiones obsoletas controlados.

## 4. Confiabilidad y seguridad · 20 puntos

- Set dorado suficiente.
- Casos normales, límite, adversariales y de fallo.
- Métricas reportadas.
- Acciones críticas protegidas fuera del prompt.
- Cola de aprobación funcional.
- Política de datos y secretos.

## 5. Producción y operación · 15 puntos

- Configuración reproducible.
- Logs y trazabilidad.
- Presupuestos, timeouts y reintentos.
- Fallback o rollback.
- Runbook de incidentes.
- Responsable operativo definido.

## 6. Economía y comunicación · 15 puntos

- Costo total razonable.
- Supuestos visibles.
- Escenarios conservador, esperado y optimista.
- Documentación utilizable.
- Demo clara con caso de fallo.
- Retrospectiva honesta.

## Escala

- **90–100:** sistema profesional, verificable y operable.
- **80–89:** sistema funcional con mejoras localizadas.
- **70–79:** prototipo útil, todavía insuficiente para operación.
- **Menos de 70:** demostración incompleta o arquitectura no confiable.

## Fallos que impiden aprobar

- secretos publicados;
- acciones críticas sin aprobación;
- ausencia de evals;
- datos inventados presentados como reales;
- arquitectura que no puede detenerse;
- documentación insuficiente para reproducir;
- proyecto que solo funciona en una demostración preparada.

## Evaluación semanal

Cada módulo se revisa mediante:

1. commit o versión;
2. demostración breve;
3. prueba de fallo;
4. decisión documentada;
5. actualización de evals.

El proyecto final integra evidencia acumulada. No reemplaza las entregas semanales.