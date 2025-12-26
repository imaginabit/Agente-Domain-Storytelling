# Domain Storytelling Master Agent

## ¿Qué es?

El **Domain Storytelling Master** es un agente especializado de Claude Code que coordina 4 skills de Domain Storytelling para análisis completo de procesos empresariales.

## Arquitectura

```
domain-storytelling-master (Agente Coordinador)
├── dominacion-lenguaje-pictografico (Skill)
├── modelado-basado-escenarios (Skill)
├── facilitacion-knowledge-crunching (Skill)
└── gestion-alcance-scope (Skill)
```

## Cómo Usarlo

### En Claude Code:

```
> Use the domain-storytelling-master agent to analyze [process]
```

### Ejemplos de Prompts:

#### 1. Análisis Básico
```
Analiza el proceso de contratación para identificar actores, actividades y objetos.
```

#### 2. Workshop Completo
```
Facilita una sesión de Domain Storytelling para optimizar el proceso de facturación.
Incluye: estado actual (As-Is), problemas identificados, y diseño futuro (To-Be).
Audiencia: RRHH + Administración + Finanzas
```

#### 3. Especificación Técnica
```
Crea especificación fine-grained del proceso de órdenes de trabajo para implementación.
Incluye: validaciones, excepciones, integraciones con ERP.
Perspectiva: To-Be (proceso futuro optimizado)
```

#### 4. Gap Analysis
```
Compara proceso actual vs futuro de solicitud de vacaciones,
mostrando diferencias, beneficios y ROI.
Granularidad: Coarse para overview, fine para áreas críticas.
```

## Flujo de Trabajo

### Fase 1: Descubrimiento (Pictographic Language)
- Extrae actores (quién)
- Identifica objetos de trabajo (qué)
- Define actividades (cómo)
- Crea tripletas: Actor → Actividad → Objeto

### Fase 2: Modelado (Scenario Modeling)
- Captura happy path (80% casos)
- Documenta variaciones como anotaciones
- Numera pasos secuencialmente
- Elimina condicionales complejos

### Fase 3: Análisis (Facilitation & Knowledge Crunching)
- Detecta plot holes e inconsistencias
- Identifica pain points
- Captura conocimiento tácito
- Documenta excepciones

### Fase 4: Optimización (Scope Management)
- Define granularidad apropiada
- Crea versión As-Is (actual)
- Diseña versión To-Be (futuro)
- Documenta gap analysis

## Tipos de Tareas

| Tipo | Propósito | Skills Principales | Audiencia |
|------|-----------|-------------------|-----------|
| **Análisis As-Is** | Documentar estado actual | Pictographic + Facilitation + Scope | Usuarios, Operadores |
| **Diseño To-Be** | Proceso futuro optimizado | Pictographic + Scenario + Scope | Desarrollo, Arquitectos |
| **Gap Analysis** | Comparar actual vs futuro | Todas | Stakeholders, Ejecutivos |
| **Workshop** | Sesión colaborativa | Facilitation (primario) | Múltiples roles |
| **Especificación** | Para implementación | Scenario (fine-grained) | Desarrolladores |

## Personalización por Audiencia

### Ejecutivos
```
"Presenta overview coarse-grained del proceso con iconos,
enfoque en ROI y timeline, comparar As-Is vs To-Be"
```

### Desarrolladores
```
"Documenta especificación fine-grained To-Be con detalles técnicos,
incluyendo APIs, validaciones, excepciones e integraciones"
```

### Usuarios Finales
```
"Modela proceso As-Is con focus en su área de trabajo,
detecta pain points y propone mejoras específicas"
```

### Audiencias Mixtas
```
"Estructura híbrida: coarse para overview, fine para áreas críticas,
con iconos visuales y ejemplos concretos"
```

## Comandos Útiles

### Cambiar Granularidad
```
"Cambia a fine-grained para el área de validación"
"Resume a coarse-grained para presentación ejecutiva"
```

### Alternar Perspectiva
```
"Ahora diseñemos To-Be basado en problemas identificados"
"Volvamos a As-Is para validar con usuarios"
```

### Detectar Problemas
```
"¿Dónde están los pain points?"
"Detecta plot holes en este flujo"
```

### Documentar Variaciones
```
"¿Qué pasa si el supervisor no está disponible?"
"Documenta la excepción para casos urgentes"
```

## Beneficios

✅ **Integral** - Combina 4 metodologías en una
✅ **Adaptable** - Se ajusta a audiencia y propósito
✅ **Visual** - Usa iconos para claridad
✅ **Iterativo** - Refina hasta capturar todo
✅ **Actionable** - Entrega resultados implementables

## Ejemplos Completos

### Ejemplo 1: Proceso de Onboarding

**Input del usuario:**
```
"Necesitamos optimizar el proceso de alta de nuevos empleados. Actualmente
toma 5-7 días y tenemos muchas quejas. ¿Puedes analizarlo?"
```

**El agente:**
1. **Pictographic:** Extrae actores (RRHH, IT, empleado, jefe), objetos (documentos, cuentas, formación), actividades (validar, crear, asignar)
2. **Scenario:** Modela happy path paso a paso
3. **Facilitation:** Identifica pain points (múltiples sistemas, dependencias manuales)
4. **Scope:** Define granularidad fine para IT, coarse para RRHH

**Output:**
```
PROCESO ACTUAL (AS-IS) - 5-7 días
👤 Candidato → 📝 Completa → 📄 Documentación
👥 RRHH → 🔍 Valida → 📄 Documentos
👥 RRHH → 📞 Contacta → 👤 IT (para cuentas)
💻 IT → ⚙️ Crea → 🔐 Cuentas manualmente (delay 2-3 días)
👤 Candidato → ⏰ Espera → 🔐 Credenciales
...

PROBLEMAS IDENTIFICADOS:
- Pain Point: Dependencia IT manual (2-3 días delay)
- Pain Point: Múltiples sistemas sin integración
- Plot Hole: ¿Qué pasa si IT no responde?

PROCESO FUTURO (TO-BE) - 1 día
👤 Candidato → 📤 Sube → 📄 Documentos digitalmente
💻 Sistema → 🤖 Valida → 📄 Automáticamente
💻 Sistema → ⚙️ Crea → 🔐 Cuentas automáticamente
👤 Candidato → 📱 Recibe → 🔐 Credenciales día 1
...
```

### Ejemplo 2: Facturación Automatizada

**Input del usuario:**
```
"Diseña proceso To-Be para facturación automatizada. Debe integrar
con ERP y reducir tiempo de 3 días a 2 horas."
```

**El agente:**
1. **Pictographic:** Define actores (técnico, sistema, cliente), objetos (órdenes, facturas, pagos)
2. **Scenario:** Modela proceso automatizado
3. **Facilitation:** Asegura que no hay gaps en automatización
4. **Scope:** Fine-grained para integraciones técnicas

**Output:**
```
PROCESO FUTURO (TO-BE) - 2 horas
👤 Técnico → ✅ Completa → 🏭 Orden de trabajo
👤 Técnico → 📱 Registra → 📝 En app móvil
💻 Sistema → 🧮 Calcula → 💰 Costes automáticamente
💻 Sistema → 🔄 Sincroniza → 📊 Con ERP
💻 Sistema → 📧 Envía → 🧾 Factura a cliente
👤 Cliente → 💳 Paga → 🧾 Online
💻 Sistema → 🗄️ Registra → 💰 Pago automáticamente

INTEGRACIONES TÉCNICAS:
- API ERP: sync órdenes completadas
- Gateway pago: procesamiento automático
- Notificaciones: email + SMS
```

## Personalización

El agente se adapta automáticamente a:
- **Audiencia:** Negocio, técnica, mixta
- **Granularidad:** Coarse (overview) o fine (detalle)
- **Perspectiva:** As-Is (actual), To-Be (futuro), híbrida
- **Propósito:** Análisis, diseño, implementación, presentación

## Tips de Uso

1. **Sé específico:** "Proceso de facturación para clientes enterprise" vs "facturación"
2. **Define audiencia:** "Para desarrollo" vs "para directivos"
3. **Establece scope:** "Solo el proceso de aprobación" vs "proceso completo"
4. **Menciona problemas conocidos:** Ayuda al agente a enfocar

## Restricciones

- No puede acceder a sistemas externos
- Requiere input textual del usuario
- Se basa en información proporcionada
- No puede validar contra sistemas reales

---

**Para más detalles:** Consulta la documentación de cada skill individual en `~/.claude/skills/`
