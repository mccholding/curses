# Módulo 3 · Datos, herramientas y MCP

**Duración:** 5 horas.

## Objetivos

- Identificar las fuentes de verdad del negocio.
- Diseñar herramientas pequeñas, claras y verificables.
- Separar lectura, propuesta y escritura.
- Entender cuándo una integración directa debe convertirse en un servidor MCP.

## Fuentes de verdad empresariales

Una fuente de verdad puede ser:

- catálogo;
- CRM;
- inventario;
- sistema financiero;
- calendario;
- base documental;
- expedientes;
- políticas;
- tabla de precios;
- sistema de pedidos.

Cada fuente debe tener propietario, fecha de actualización, alcance y política de acceso.

## Diseño de herramientas

Una herramienta debe representar una acción concreta.

Buena separación:

```text
consultar_cliente
consultar_saldo
preparar_recordatorio
solicitar_aprobacion_envio
```

Mala separación:

```text
gestionar_todo_el_cliente
```

La descripción de una herramienta debe decir:

- qué hace;
- cuándo usarla;
- cuándo no usarla;
- qué datos exige;
- qué devuelve;
- qué errores puede producir.

## Errores útiles

En lugar de devolver solamente “error”, una herramienta debe ayudar al agente a decidir:

```json
{
  "error": "SKU no encontrado",
  "similares": ["FER-001", "FER-003"],
  "accion_recomendada": "pedir al usuario categoría o uso"
}
```

## Lectura frente a escritura

| Tipo | Ejemplo | Control recomendado |
|---|---|---|
| Lectura | consultar stock | autónomo con log |
| Propuesta | preparar orden | autónomo, sin ejecutar |
| Escritura reversible | actualizar estado | validación y trazabilidad |
| Escritura sensible | cambiar precio | aprobación humana |
| Acción crítica | pagar o eliminar | el agente prepara; una persona ejecuta |

## MCP

MCP permite exponer datos y herramientas mediante una interfaz reutilizable para distintos agentes o clientes compatibles.

Conviene considerar MCP cuando:

- varios agentes necesitan la misma integración;
- se requiere separar la lógica de negocio del agente;
- existen varias aplicaciones consumidoras;
- se quiere administrar permisos y herramientas desde un punto común.

No es obligatorio para una primera prueba. Una función local puede ser suficiente.

## FerreAgente

El caso desarrolla herramientas para:

- consultar stock;
- detectar productos bajo mínimo;
- analizar rotación;
- registrar entradas;
- sugerir reorden.

La escritura de inventario exige validación. La orden de compra se prepara, pero queda pendiente de aprobación.

## Construcción

```text
datos/fuentes.md
datos/base-principal.db
herramientas/README.md
herramientas/consultas.*
herramientas/acciones.*
configuracion/permisos.md
```

## Pruebas

- dato existente;
- dato inexistente;
- consulta ambigua;
- valor fuera de rango;
- fuente desactualizada;
- herramienta caída;
- intento de escritura sin autorización;
- respuesta parcial.

## Entregable

Dos fuentes documentadas, al menos tres herramientas de lectura, una acción controlada y una decisión justificada sobre usar o no MCP.