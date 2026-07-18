# Módulo 2 · Primer agente funcional

**Duración:** 5 horas.

## Objetivos

- Comprender el ciclo agéntico construyéndolo una vez.
- Conectar un modelo con herramientas y una fuente de datos.
- Diseñar errores útiles y pruebas de aceptación.
- Implementar la misma arquitectura con código o low-code.

## Ciclo agéntico

```text
recibir objetivo
→ decidir si necesita una herramienta
→ solicitar la herramienta
→ ejecutar
→ observar el resultado
→ responder, corregir o escalar
```

El agente no es el `while` por sí solo. Es la combinación de modelo, instrucciones, contexto, herramientas, estado, verificación y límites.

## Arquitectura mínima

```text
Usuario
  ↓
Agente
  ├── instrucciones
  ├── historial o estado
  ├── herramienta de consulta
  ├── herramienta de acción
  └── escalamiento humano
```

## FerreAgente

El agente vendedor consulta un catálogo antes de mencionar precio o disponibilidad, crea cotizaciones cuando el cliente confirma cantidades y escala solicitudes de crédito, devoluciones, pedidos grandes o descuentos fuera de política.

Pruebas mínimas:

1. consulta válida;
2. recomendación técnica;
3. cotización con varias líneas;
4. datos insuficientes;
5. elemento inexistente;
6. manipulación de políticas;
7. escalamiento correcto;
8. herramienta con error.

## Transferencia

### Consultora

- `buscar_servicio`;
- `consultar_tarifa`;
- `crear_borrador_propuesta`;
- `escalar_al_consultor`.

### Academia

- `buscar_programa`;
- `consultar_requisitos`;
- `crear_plan_orientacion`;
- `escalar_a_coordinacion`.

### Ecommerce

- `buscar_producto`;
- `consultar_pedido`;
- `crear_solicitud_devolucion`;
- `escalar_a_soporte`.

## Ruta con código

Construir el loop de herramientas directamente con el SDK del proveedor elegido. Separar:

- funciones de negocio;
- esquemas visibles para el modelo;
- ciclo de ejecución;
- interfaz de usuario;
- logs.

Nunca guardar claves en el repositorio. Usar variables de entorno.

## Ruta low-code

Replicar la arquitectura con:

- nodo de entrada;
- nodo de agente o modelo;
- herramientas conectadas;
- base de datos o tabla;
- condición de escalamiento;
- registro de ejecución.

El estándar de pruebas es idéntico en ambas rutas.

## Construcción

```text
datos/fuente-inicial.csv o .db
agentes/agente-inicial.py o workflow exportado
herramientas/consultar.py
herramientas/accion.py
observabilidad/ejecuciones.log
```

## Entregable

Agente que pasa al menos ocho pruebas de aceptación, con evidencia de uso correcto de herramientas y dos escalamientos humanos.