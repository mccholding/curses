# 🔵 NIVEL 2 — CONECTAR Y POTENCIAR
*Darle a la IA acceso a tus herramientas y tus métodos de trabajo.*

## 2.1 MCP: el conector universal

### La explicación sencilla

**MCP** (*Model Context Protocol*) es el estándar que permite conectar la IA con otras aplicaciones: tu correo, tu calendario, bases de datos, Canva, Figma, GitHub y cientos más. Lo creó Anthropic y lo adoptó toda la industria.

### La mejor analogía: el puerto USB-C 🔌

Antes del USB-C, cada aparato tenía su propio cable. Un caos. Antes de MCP pasaba lo mismo: cada conexión IA-aplicación era un desarrollo a la medida. **MCP es el USB-C de la IA:** un solo estándar para conectar cualquier modelo con cualquier herramienta.

```
                    ┌──────────────┐
                    │              │──── MCP ───→ 📧 Gmail
                    │    CLAUDE    │──── MCP ───→ 📅 Calendario
   Tú ── chat ────→ │    (LLM)     │──── MCP ───→ 🎨 Canva
                    │              │──── MCP ───→ 🗄️ Base de datos
                    │              │──── MCP ───→ 📁 Google Drive
                    └──────────────┘
```

### Vocabulario clave

- **Servidor MCP:** cada conexión individual (el servidor MCP de Gmail, el de Canva...). En las apps de consumo suelen llamarse **conectores**.
- Tú decides **qué conectar y con qué permisos**. La IA solo toca lo que tú le conectas.

### Ejemplo práctico

Con Gmail y Calendario conectados:

```
Tú: Revisa mis correos de esta semana, encuentra las reuniones
    que me propusieron y agéndalas donde tenga espacio libre.

IA: [lee correos vía MCP] → [detecta 3 propuestas] →
    [consulta tu calendario vía MCP] → [encuentra huecos] →
    "Encontré 3 reuniones. ¿Confirmo estos horarios?"
```

Sin MCP, esto sería copiar y pegar correo por correo. Con MCP, es una sola instrucción.

> 🎯 **Hazlo tú ahora (3-5 min):** abre el directorio de conectores de tu app de IA y explóralo 5 minutos. Conecta UNO de bajo riesgo (calendario, por ejemplo) y pide: "¿qué tengo agendado mañana?"
>
> ⚠️ **Error común:** conectar todo con todos los permisos el primer día. Más conexiones no es más productividad: es más superficie de riesgo.
>
> ✅ **Buena práctica:** conecta por necesidad real, con permisos mínimos, y empieza con acceso de solo lectura cuando sea posible.


---

## 2.2 Skills: los manuales de procedimientos

### La explicación sencilla

Una **Skill** es un **manual de procedimientos** para la IA: una carpeta con instrucciones (y opcionalmente plantillas o scripts) que le enseñan a hacer una tarea específica **a tu manera**.

El empleado nuevo es brillante, pero no sabe que tus reportes llevan cierto formato o que tus propuestas siguen cierta estructura. Una Skill es el documento de "así hacemos las cosas aquí".

### Anatomía de una Skill

```
mi-skill-de-reportes/
└── SKILL.md          ← las instrucciones
└── plantilla.docx    ← (opcional) archivos de apoyo
└── ejemplos/         ← (opcional) ejemplos de referencia
```

El archivo `SKILL.md`:

```markdown
---
name: reporte-semanal
description: Crea el reporte semanal de ventas con el formato de la empresa
---

# Reporte Semanal de Ventas

Cuando el usuario pida el reporte semanal:
1. Usa la plantilla incluida en esta carpeta
2. Estructura: Resumen → Métricas → Riesgos → Próximos pasos
3. Cifras en formato $1,234.56 MXN
4. Tono directo, máximo 2 páginas
```

### Por qué es tan poderoso

- **Consistencia:** la tarea sale igual todas las veces, sin repetir instrucciones
- **Conocimiento acumulado:** capturas la experiencia del equipo en archivos reutilizables
- **Se comparten:** tu Skill la puede usar todo tu equipo
- **Se activan solas:** la IA detecta cuándo aplican y las usa automáticamente

### El antes y el después

```
SIN skill:  "Hazme el reporte... recuerda formato X, secciones Y,
             cifras en pesos, 2 páginas..." (CADA semana)

CON skill:  "Hazme el reporte semanal con estos datos."  →  perfecto a la primera
```

> 💡 **Regla del 3:** cualquier instrucción que hayas repetido 3 veces merece convertirse en Skill.

> 🎯 **Hazlo tú ahora (3-5 min):** identifica LA instrucción que más repites en tu trabajo y escríbele su SKILL.md de máximo 10 líneas usando el formato de esta sección. Acabas de crear tu primer activo de IA.
>
> ⚠️ **Error común:** la skill enciclopedia: 300 líneas que mezclan cinco tareas distintas y que nadie mantiene. La IA se confunde igual que un empleado con un manual caótico.
>
> ✅ **Buena práctica:** una skill = una tarea. Nombre claro y una descripción que diga exactamente cuándo debe activarse.


---

## 2.3 Plugins: paquetes de capacidades

### La explicación sencilla

Un **plugin** es un **paquete instalable** que puede agrupar varias cosas a la vez: Skills + comandos + agentes + conexiones MCP. Instalas una vez y toda esa capacidad queda disponible.

### Analogía: la app store de tu IA 📦

- Una **Skill** = una receta
- Un **servidor MCP** = un electrodoméstico conectado
- Un **plugin** = el kit completo de cocina italiana: recetas + utensilios + ingredientes en una caja

### Ejemplo

Un plugin "asistente-de-marketing" podría incluir al instalarse:

- ✅ Skill para redactar posts con el tono de tu marca
- ✅ Skill para calendarios de contenido
- ✅ Comando `/campaña` para generar campañas completas
- ✅ Conexión MCP a tu herramienta de redes sociales

> 🎯 **Hazlo tú ahora (3-5 min):** explora el catálogo de plugins de tu herramienta y encuentra uno relacionado con tu rol. Antes de instalarlo, revisa qué trae dentro (qué skills, qué comandos, qué conexiones).
>
> ⚠️ **Error común:** instalar de todo "por si acaso". Cada plugin agrega herramientas al escritorio de la IA: demasiados = ruido y confusión.
>
> ✅ **Buena práctica:** instala lo que vas a usar esta semana; desinstala lo que no usaste este mes.


---

## 2.4 API: qué es y por qué la mencionan tanto

### La explicación sencilla

**API** (*Application Programming Interface*) es la forma en que **los programas hablan entre sí**. La API de Anthropic es la "puerta de servicio" por la que cualquier aplicación puede usar a Claude directamente, sin pasar por la ventana del chat.

### La analogía del restaurante 🍽️

- **El chat (Claude.ai)** = comer en el restaurante: mesa puesta, mesero, menú, ambiente
- **La API** = la cocina con servicio a domicilio: cualquier negocio puede pedirle platillos a la cocina e integrarlos en su propia operación

### Por qué te importa aunque no programes

1. **Explica el ecosistema:** cuando una app dice "con IA integrada", casi siempre está usando la API de algún LLM por detrás.
2. **Explica los tokens como costo:** la API cobra por tokens procesados. Por eso todo el mundo habla de tokens.
3. **Abre posibilidades futuras:** si algún día tu empresa quiere IA dentro de sus propios sistemas, el camino es la API (y no necesitas ser tú quien programe — necesitas saber que existe para pedirla).

> 📖 Documentación oficial: https://docs.claude.com/en/api/overview

> 🎯 **Hazlo tú ahora (3-5 min):** identifica 2 aplicaciones que ya uses que anuncien "IA integrada" y pregúntate: ¿qué modelo habrá detrás? ¿qué le estarán enviando? Empezarás a ver el ecosistema con rayos X.
>
> ⚠️ **Error común:** creer que "necesitamos IA en la empresa" significa un proyecto gigante de meses. Muchas veces es una API + un buen prompt + una tarde de trabajo.
>
> ✅ **Buena práctica:** cuando hables con proveedores o con tu equipo técnico, pregunta siempre: "¿qué modelo usa por detrás y qué pasa con nuestros datos?"


---

### ✅ Checkpoint del Nivel 2

Tu "empleado" ya tiene: acceso a tus herramientas (**MCP**), tus manuales de procedimientos (**Skills**), kits completos instalables (**plugins**) y entiendes cómo la IA se integra en cualquier software (**API**). Ahora viene el gran salto mental: **dejar de pedirle cosas y empezar a delegarle trabajo.**

---
---
