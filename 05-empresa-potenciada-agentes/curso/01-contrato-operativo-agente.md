# Módulo 1 · Contrato operativo del agente

**Duración:** 4 horas.

## Objetivos

- Aplicar Prompt, Context y Loop Engineering a un agente real.
- Definir políticas, límites, escalamiento y criterios de éxito.
- Versionar instrucciones mediante pruebas adversariales.

## De prompt a contrato operativo

Un agente empresarial necesita más que una descripción de rol.

```text
ROL
OBJETIVO
USUARIOS
FUENTES DE VERDAD
HERRAMIENTAS
POLÍTICAS
LÍMITES
ESCALAMIENTO
CRITERIOS DE CALIDAD
CONDICIÓN DE PARADA
```

## Principio general

Las instrucciones deben resolver conflictos previsibles. Una regla como “no ofrezcas descuentos no autorizados” es débil si no define:

- límite exacto;
- fuente de la autorización;
- comportamiento ante insistencia;
- momento de escalamiento;
- acción posterior al escalamiento.

Las restricciones críticas también deben vivir en el código o la herramienta. El prompt guía; el sistema impide.

## FerreAgente

El caso desarrolla tres versiones del agente vendedor “Toño”:

- **V1:** rol general, sin fuentes ni límites.
- **V2:** catálogo, descuentos y longitud.
- **V3:** herramientas obligatorias, políticas innegociables, motivos codificados de escalamiento y formato de cotización.

Pruebas adversariales:

- cliente apurado;
- cliente técnico;
- manipulación por descuento;
- producto fuera de catálogo;
- reclamo;
- solicitud de crédito.

## Transferencia

| Sector | Agente inicial | Fuente de verdad | Acción sensible |
|---|---|---|---|
| Consultora | creador de propuestas | servicios, tarifas y casos | comprometer alcance o precio |
| Academia | orientador académico | programas y políticas | admisión o calificación |
| Ecommerce | soporte | catálogo, pedidos y devoluciones | reembolso |
| Recursos humanos | filtro inicial | perfil y criterios | rechazo definitivo |

## Construcción

Crear:

```text
prompts/agente-v1.md
prompts/agente-v2.md
prompts/agente-v3.md
prompts/CHANGELOG.md
configuracion/ficha-agente.md
```

## Plantilla mínima

```markdown
# Rol
# Objetivo observable
# Usuarios
# Contexto del negocio
# Fuentes de verdad
# Herramientas y cuándo usarlas
# Políticas
# Acciones prohibidas
# Escalamiento
# Formato de salida
# Verificación
# Condiciones de parada
```

## Práctica

1. Diseñar V1.
2. Ejecutar cinco casos normales.
3. Ejecutar cinco casos adversariales.
4. Registrar cada fallo.
5. Crear V2 y V3 con cambios justificables.
6. Comparar resultados.

## Entregable

Contrato operativo V3, changelog y matriz que conecta cada regla con una prueba que demuestra su necesidad.