# 📚 Índice Completo - Domain Storytelling en Claude Code

## 🎯 Introducción

Este conjunto de herramientas proporciona un sistema completo de **Domain Storytelling** para Claude Code, incluyendo 4 skills especializadas y un agente maestro que las coordina.

---

## 🗂️ Estructura de Archivos

### Agente Principal
```
~/.claude/agents/domain-storytelling-master.md
```
**Descripción:** Agente coordinador que usa las 4 skills según necesidad
**Cómo usar:** `> Use the domain-storytelling-master agent to analyze [proceso]`

---

### 📖 Documentación del Agente

#### 1. README Principal
```
~/.claude/agents/README-domain-storytelling.md
```
**Contenido:**
- Qué es el agente
- Cómo usarlo
- Ejemplos de prompts
- Tipos de tareas
- Personalización por audiencia

#### 2. Ejemplo Práctico Completo
```
~/.claude/agents/ejemplo-practico-ordenes-trabajo.md
```
**Contenido:**
- Sesión completa paso a paso
- Input del usuario
- Output del agente
- Múltiples formatos de salida (ejecutivo, técnico, operativo)
- Gap analysis
- ROI calculation

---

### 🛠️ Skills Especializadas

#### 1. Pictographic Language
```
~/.claude/skills/dominacion-lenguaje-pictografico/
├── SKILL.md                           (Main file, actualizado con SVG)
├── assets/
│   ├── README.md                      (Documentación SVG)
│   ├── actores/
│   │   ├── person.svg                 (👤)
│   │   ├── group.svg                  (👥)
│   │   └── system.svg                 (💻)
│   └── objetos/
│       ├── document.svg               (📄)
│       ├── folder.svg                 (📁)
│       ├── call.svg                   (📞)
│       ├── email.svg                  (✉️)
│       ├── form.svg                   (📝)
│       ├── database.svg               (🗄️)
│       ├── report.svg                 (📊)
│       ├── money.svg                  (💰)
│       ├── cart.svg                   (🛒)
│       └── calendar.svg               (📅)
└── referencias/
    ├── iconos-visualizacion.md        (Guía de uso de SVG)
    ├── ejemplos-procesos-empresariales.md
    ├── plantillas-tripletas.md
    ├── casos-uso-rrhh.md
    └── casos-uso-ordenes.md
```

**Propósito:** Extraer actores, objetos y actividades de procesos
**Salida:** Tripletas estructuradas (Actor → Actividad → Objeto)

#### 2. Scenario Modeling
```
~/.claude/skills/modelado-basado-escenarios/
├── SKILL.md
└── referencias/
    ├── ejemplos-happy-path.md
    ├── eliminacion-condicionales.md
    ├── numeracion-secuencial.md
    └── variaciones-anotaciones.md
```

**Propósito:** Modelar flujos principales y variaciones
**Salida:** Proceso paso a paso con numeración y anotaciones

#### 3. Facilitation & Knowledge Crunching
```
~/.claude/skills/facilitacion-knowledge-crunching/
├── SKILL.md
└── referencias/
    ├── deteccion-plot-holes.md
    ├── sistema-anotaciones.md
    ├── identificacion-pain-points.md
    ├── knowledge-crunching.md
    └── ejemplos-facilitacion.md
```

**Propósito:** Facilitar sesiones y capturar conocimiento tácito
**Salida:** Problemas identificados, plot holes, knowledge tácito

#### 4. Scope Management
```
~/.claude/skills/gestion-alcance-scope/
├── SKILL.md
└── referencias/
    ├── granularidad-pajaro-vs-mar.md
    ├── as-is-vs-to-be.md
    ├── audiencias-y-scope.md
    ├── ejemplos-cambio-granularidad.md
    └── gestion-expectativas.md
```

**Propósito:** Gestionar granularidad y perspectivas temporales
**Salida:** Definición de nivel de detalle y perspectiva (As-Is/To-Be)

---

## 🚀 Guía de Uso Rápido

### Para Empezar

#### Opción 1: Análisis Simple
```
> Use the domain-storytelling-master agent to analyze our hiring process
```

#### Opción 2: Workshop Completo
```
> Use the domain-storytelling-master agent to facilitate a Domain Storytelling
  workshop for our invoice process with Sales, Operations, and Finance teams.
  Include: As-Is analysis, problem identification, and To-Be design.
```

#### Opción 3: Especificación Técnica
```
> Use the domain-storytelling-master agent to create a fine-grained To-Be
  specification for our work order system for development team.
  Include: APIs, validations, exceptions, and integrations.
```

### Ejemplos por Dominio

#### RRHH
```
> Use the domain-storytelling-master agent to optimize employee onboarding
  process. Focus on As-Is analysis to identify delays.
```

#### Ventas
```
> Use the domain-storytelling-master agent to design To-Be sales process
  with automation. Audience: Sales team + Development
```

#### Operaciones
```
> Use the domain-storytelling-master agent to document current fulfillment
  workflow with coarse granularity for executives
```

#### Finanzas
```
> Use the domain-storytelling-master agent to create automated invoicing
  process specification with fine-grained detail for development
```

---

## 🎨 Iconos SVG

### Ubicación
```
~/.claude/skills/dominacion-lenguaje-pictografico/assets/
```

### Actores (3 iconos)
| Icono | Archivo | Uso |
|-------|---------|-----|
| 👤 | `actores/person.svg` | Persona individual |
| 👥 | `actores/group.svg` | Grupo o equipo |
| 💻 | `actores/system.svg` | Sistema automatizado |

### Objetos de Trabajo (10 iconos)
| Icono | Archivo | Uso |
|-------|---------|-----|
| 📄 | `objetos/document.svg` | Documentos |
| 📁 | `objetos/folder.svg` | Archivos/carpetas |
| 📞 | `objetos/call.svg` | Comunicaciones |
| ✉️ | `objetos/email.svg` | Emails |
| 📝 | `objetos/form.svg` | Formularios |
| 🗄️ | `objetos/database.svg` | Bases de datos |
| 📊 | `objetos/report.svg` | Reportes |
| 💰 | `objetos/money.svg` | Transacciones financieras |
| 🛒 | `objetos/cart.svg` | Pedidos |
| 📅 | `objetos/calendar.svg` | Eventos |

### Cómo Usar en HTML
```html
<img src="assets/actores/person.svg" width="20"> Empleado
<img src="assets/objetos/form.svg" width="20"> Formulario
```

### Formato en Diagramas
```markdown
👤 Empleado → 📝 Completa → 📄 Formulario
👥 RRHH → ✅ Valida → 📄 Solicitud
💻 Sistema → 🔄 Procesa → 📊 Datos
```

---

## 📋 Flujo de Trabajo Típico

### 1. Análisis As-Is (Estado Actual)
**Prompt:**
```
Documenta cómo funciona actualmente el proceso de [X],
identificando problemas y oportunidades de mejora.
```

**El agente usará:**
- Pictographic Language (extraer elementos)
- Facilitation (detectar pain points)
- Scope Management (coarse-grained)

### 2. Diseño To-Be (Estado Futuro)
**Prompt:**
```
Diseña cómo debería funcionar el proceso de [X] de manera optimizada
y automatizada.
```

**El agente usará:**
- Pictographic Language (estructura)
- Scenario Modeling (flujo optimizado)
- Scope Management (fine-grained)

### 3. Gap Analysis (Comparativo)
**Prompt:**
```
Compara proceso actual vs futuro para [X], mostrando diferencias,
beneficios y ROI.
```

**El agente usará:**
- Todas las skills
- Scope Management (híbrido: coarse + fine)

### 4. Workshop Facilitation
**Prompt:**
```
Facilita sesión de Domain Storytelling con [stakeholders]
para capturar proceso de [X].
```

**El agente usará:**
- Facilitation (primario)
- Las demás según emergen

### 5. Especificación para Desarrollo
**Prompt:**
```
Crea especificación detallada del proceso de [X] para implementación técnica.
Incluye: APIs, validaciones, excepciones.
```

**El agente usará:**
- Scenario Modeling (fine-grained)
- Pictographic
- Scope (técnico)

---

## 👥 Adaptación por Audiencia

### Ejecutivos
**Características:**
- Tiempo: 30-60 minutos
- Granularidad: Coarse-grained
- Perspectiva: As-Is + To-Be
- Output: Dashboard, ROI

**Prompt recomendado:**
```
> Use the domain-storytelling-master agent to create a high-level
  overview of [process] comparing current state vs future state.
  Focus on ROI and benefits. Audience: C-level executives.
```

### Desarrolladores
**Características:**
- Tiempo: 2-4 horas
- Granularidad: Fine-grained
- Perspectiva: To-Be
- Output: Especificaciones técnicas

**Prompt recomendado:**
```
> Use the domain-storytelling-master agent to create a detailed
  technical specification of [process] for implementation.
  Include: happy path, variations, validations, exceptions,
  API endpoints, and integrations. Audience: Development team.
```

### Usuarios Finales
**Características:**
- Tiempo: 1-2 horas
- Granularidad: Fine en su área
- Perspectiva: As-Is + mejoras
- Output: Guía de trabajo

**Prompt recomendado:**
```
> Use the domain-storytelling-master agent to document the [process]
  focusing on my daily work. Identify pain points and propose
  improvements. Audience: End users in [department].
```

### Stakeholders Mixtos
**Características:**
- Tiempo: 90 minutos
- Granularidad: Híbrida
- Perspectiva: Ambos
- Output: Múltiples formatos

**Prompt recomendado:**
```
> Use the domain-storytelling-master agent to facilitate a session
  for [process] with mixed audience (business + technical).
  Provide: executive summary (coarse) + technical details (fine).
```

---

## 🔧 Personalización Avanzada

### Cambiar Granularidad Durante Sesión
```
"Cambia a fine-grained en el área de validación"
"Resume a coarse-grained para la presentación"
```

### Alternar Perspectiva Temporal
```
"Ahora diseñemos To-Be basado en los problemas identificados"
"Volvamos a As-Is para validar con los usuarios"
```

### Detectar Problemas Específicos
```
"¿Dónde están los pain points en este proceso?"
"Detecta plot holes en el flujo descrito"
"¿Qué excepciones debemos considerar?"
```

### Documentar Variaciones
```
"¿Qué pasa si el supervisor no está disponible?"
"¿Cómo manejamos casos urgentes?"
"Documenta la variación para clientes VIP"
```

---

## 📊 Tipos de Output

### Para Negocio
- Diagramas con iconos SVG
- Identificación de problemas
- Propuestas de mejora
- Timeline de implementación

### Para Desarrollo
- Especificaciones detalladas
- Happy path + variaciones
- Validaciones y excepciones
- Integraciones necesarias

### Para Ejecutivos
- Visión general clara
- Gap As-Is vs To-Be
- ROI y beneficios
- Roadmap de mejoras

---

## 💡 Tips y Best Practices

### Para Mejores Resultados

1. **Sé específico en el prompt**
   - ✅ "Analiza el proceso de onboarding para empleados de ventas"
   - ❌ "Analiza el proceso de RRHH"

2. **Define la audiencia**
   - ✅ "Para el equipo de desarrollo"
   - ❌ "Para todos"

3. **Menciona problemas conocidos**
   - ✅ "Actualmente toma 5 días y hay múltiples handoffs"
   - ❌ "Optimizar el proceso"

4. **Especifica el propósito**
   - ✅ "Diseñar proceso To-Be para automatización"
   - ❌ "Documentar el proceso"

### Para Facilitación Efectiva

1. **Empieza con expectativas**
   - "¿Qué esperas lograr con este análisis?"

2. **Define granularidad**
   - "¿Visión general o detalle paso a paso?"

3. **Establece perspectiva**
   - "¿Cómo es ahora o cómo debería ser?"

4. **Captura happy path primero**
   - "Empecemos con el 80% de casos"

5. **Agrega variaciones después**
   - "¿Qué pasa si...?"

### Para Presentaciones

1. **Usa iconos** - Más claro visualmente
2. **Coarse para overview** - Evita overwhelm
3. **Fine solo en áreas críticas** - Mantén focus
4. **As-Is + To-Be** - Muestra problema + solución
5. **ROI visible** - Justifica inversión

---

## 📚 Recursos Adicionales

### Documentación por Skill

Cada skill tiene su propia documentación detallada en:
```
~/.claude/skills/[skill-name]/referencias/
```

### Ejemplos por Dominio

- **RRHH:** `casos-uso-rrhh.md`
- **Órdenes:** `casos-uso-ordenes.md`
- **Procesos:** `ejemplos-procesos-empresariales.md`

### Técnicas Específicas

- **Granularidad:** `granularidad-pajaro-vs-mar.md`
- **Perspectivas:** `as-is-vs-to-be.md`
- **Facilitación:** `ejemplos-facilitacion.md`
- **Variaciones:** `variaciones-anotaciones.md`

---

## 🎓 Próximos Pasos

### Para Implementar en tu Organización

1. **Identifica proceso crítico** - Empieza con uno simple
2. **Invita stakeholders clave** - 3-5 personas máximo
3. **Reserva 90 minutos** - Sesión completa
4. **Prepara contexto** - Documenta situación actual
5. **Itera** - Refina hasta capturar todo

### Para Capacitar al Equipo

1. **Comparte ejemplos** - Usa `ejemplo-practico-ordenes-trabajo.md`
2. **Practica con casos simples** - Empieza con procesos básicos
3. **Documenta learnings** - Crea ejemplos propios
4. **Escala gradualmente** - Aumenta complejidad

### Para Integrar con Desarrollo

1. **Especificación técnica** - Solicita fine-grained To-Be
2. **Validación con usuarios** - Confirma As-Is
3. **Prototipo rápido** - Implementa happy path
4. **Iteración** - Agrega variaciones
5. **Go live** - Despliega versión completa

---

## ❓ Preguntas Frecuentes

**P: ¿Puedo usar el agente sin conocer Domain Storytelling?**
R: Sí, el agente está diseñado para guiarte. Solo describe tu proceso.

**P: ¿Qué pasa si tengo audiencia mixta?**
R: El agente adapta automáticamente. Especifica "mixed audience" en el prompt.

**P: ¿Puedo cambiar granularidad durante la sesión?**
R: Sí, usa comandos como "cambia a fine-grained" en el área específica.

**P: ¿Cuánto tiempo toma un análisis completo?**
R: 90 minutos para workshop completo. 30-60 min para análisis As-Is.

**P: ¿Puedo usar solo una skill específica?**
R: Sí, pero el agente maestro las coordina mejor. Puedes solicitar "usa solo pictographic language".

---

## 📞 Soporte

Para dudas sobre:
- **Skills individuales:** Consulta `~/.claude/skills/[skill]/referencias/`
- **Uso del agente:** Consulta `~/.claude/agents/README-domain-storytelling.md`
- **Ejemplos prácticos:** Consulta `~/.claude/agents/ejemplo-practico-ordenes-trabajo.md`

---

**🎯 ¡Listo para empezar!**

```
> Use the domain-storytelling-master agent to analyze [tu proceso aquí]
```

---

*Última actualización: Diciembre 2024*
*Versión: 1.0*
*Idioma: Español*
