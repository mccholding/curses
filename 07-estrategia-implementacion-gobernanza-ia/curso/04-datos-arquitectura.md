# Módulo 4 · Datos y arquitectura

## Pregunta directiva

¿Qué datos puede utilizar el sistema, bajo qué permisos y con qué arquitectura de control?

## Objetivos

- identificar fuentes de verdad;
- clasificar datos por sensibilidad;
- limitar acceso al mínimo necesario;
- separar lectura, recomendación y escritura;
- diseñar trazabilidad y retiro de acceso.

## Mapa de datos

Para cada fuente documentar:

- dueño;
- propósito original;
- calidad y vigencia;
- sensibilidad;
- base jurídica o autorización aplicable;
- usuarios autorizados;
- sistemas conectados;
- retención;
- ubicación;
- restricciones contractuales;
- procedimiento de corrección y eliminación.

## Arquitectura mínima

```text
USUARIO AUTORIZADO
→ interfaz
→ política y autenticación
→ modelo o workflow
→ recuperación de fuentes
→ herramientas permitidas
→ validación
→ aprobación cuando corresponda
→ registro y monitoreo
```

## Principios

1. **Fuente de verdad explícita.** El modelo no sustituye el sistema de registro.
2. **Mínimo privilegio.** Acceso solo a datos y acciones indispensables.
3. **Separación de funciones.** Consultar, recomendar y ejecutar tienen riesgos diferentes.
4. **Datos representativos.** Un piloto no se evalúa con ejemplos demasiado limpios.
5. **Trazabilidad.** Poder reconstruir entradas, versiones, fuentes, decisiones y acciones.
6. **Retiro de acceso.** Desconectar debe ser posible y estar probado.
7. **Portabilidad.** Evitar que conocimiento crítico quede atrapado en una plataforma.

## Taller

Construir:

- mapa de fuentes;
- matriz de clasificación;
- diagrama de acceso;
- lista de datos prohibidos o restringidos;
- política de retención;
- flujo de corrección.

## Entregable

`mapa-datos-arquitectura.md`

## Pruebas

- usuario sin permiso solicita información sensible;
- documento obsoleto contradice una política vigente;
- el proveedor cambia su tratamiento de datos;
- una persona pide corregir o eliminar información;
- la integración entrega datos incompletos.

## Error frecuente

Conectar una carpeta completa porque resulta más rápido que seleccionar las fuentes necesarias. La conveniencia inicial puede multiplicar exposición, ruido y errores.
