# Ejemplo Práctico: Proceso de Órdenes de Trabajo

Este documento muestra una sesión completa con el **Domain Storytelling Master Agent**, desde la solicitud inicial hasta la entrega de resultados.

---

## Solicitud Inicial del Usuario

```
> Use the domain-storytelling-master agent to analyze and optimize our work order process.

Current situation:
- Takes 5-7 days from request to completion
- Many manual steps and handoffs
- Customers complain about delays
- We want to automate and streamline

Stakeholders: Sales team, Operations, Technicians, Administration
Purpose: Design an optimized To-Be process
```

---

## Respuesta del Agente

### Fase 1: Descubrimiento (Pictographic Language)

**El agente extrae actores, objetos y actividades:**

#### ACTORES IDENTIFICADOS:
- 👤 **Cliente** - Solicita servicio
- 👥 **Comercial** - Evalúa y presupuesto
- 👥 **Operaciones** - Asigna recursos
- 👤 **Técnico** - Ejecuta trabajo
- 👥 **Administración** - Facturación
- 💻 **Sistema** - Automatización

#### OBJETOS DE TRABAJO:
- 📝 Solicitud de servicio
- 💰 Presupuesto
- 📅 Orden de trabajo
- 🏭 Trabajo realizado
- 🧾 Factura
- 💰 Pago

#### ACTIVIDADES CLAVE:
- Solicitar, evaluar, presupuestar, aprobar, asignar, ejecutar, documentar, facturar, cobrar

**Estructura inicial:**
```
👤 Cliente → 📞 Solicita → 🛠️ Servicio
👥 Comercial → 📋 Evalúa → 📝 Solicitud
👥 Comercial → 💰 Prepara → 💰 Presupuesto
👤 Cliente → ✅ Aprueba → 💰 Presupuesto
👥 Operaciones → 👤 Asigna → 🔧 Técnico
👤 Técnico → 🏭 Realiza → 🛠️ Servicio
👤 Técnico → ✍️ Documenta → 📝 Trabajo
💻 Sistema → 🧮 Calcula → 💰 Costes
👥 Administración → 📧 Envía → 🧾 Factura
👤 Cliente → 💳 Paga → 🧾 Factura
```

---

### Fase 2: Modelado (Scenario Modeling)

**El agente modela el happy path y variaciones:**

```
PROCESO: Órdenes de Trabajo - Happy Path

PASO 1: Cliente solicita servicio
  1.1. Cliente completa formulario web
  1.2. Sistema registra solicitud
  1.3. Comercial recibe notificación

PASO 2: Comercial evalúa solicitud
  2.1. Comercial agenda llamada discovery
  2.2. Comercial contacta cliente
  2.3. Comercial identifica necesidades
  2.4. Comercial evalúa viabilidad técnica
  2.5. Comercial consulta disponibilidad recursos

PASO 3: Comercial prepara presupuesto
  3.1. Sistema calcula costes automáticamente
  3.2. Comercial revisa y ajusta precio
  3.3. Comercial envía presupuesto a cliente
  3.4. Cliente recibe presupuesto

PASO 4: Cliente aprueba presupuesto
  4.1. Cliente revisa presupuesto
  4.2. Cliente aprueba (online o firma)
  4.3. Sistema convierte a orden de trabajo

PASO 5: Operaciones asigna técnico
  5.1. Sistema sugiere técnico óptimo (IA)
  5.2. Operaciones confirma asignación
  5.3. Técnico recibe notificación push

PASO 6: Técnico ejecuta trabajo
  6.1. Técnico confirma recepción
  6.2. Técnico va al lugar
  6.3. Técnico realiza trabajo
  6.4. Técnico documenta en app móvil

PASO 7: Sistema genera factura
  7.1. Sistema calcula costes finales
  7.2. Sistema genera factura
  7.3. Sistema envía a cliente

PASO 8: Cliente paga factura
  8.1. Cliente recibe factura
  8.2. Cliente paga (online/transferencia)
  8.3. Sistema registra pago

VARIACIONES:
↳ 2.3.1. Si solicitud compleja: Técnico senior involvement
↳ 3.2.1. Si precio > X: Requiere aprobación gerencia
↳ 4.2.1. Si cliente no responde: Follow-up automático (3 intentos)
↳ 5.2.1. Si técnico no disponible: Asigna alternativo
↳ 6.3.1. Si trabajo adicional: Técnico solicita aprobación cliente
```

---

### Fase 3: Análisis (Facilitation & Knowledge Crunching)

**El agente detecta problemas y conocimiento tácito:**

```
PLOT HOLES DETECTADOS:

1. "¿Quién valida que el técnico completó el trabajo correctamente?"
   → ANOTACIÓN: Cliente debe aprobar antes de facturación
   → IMPACTO: Evita disputas y retrabajos

2. "¿Qué pasa si el técnico encuentra problemas adicionales?"
   → ANOTACIÓN: Proceso de "trabajo adicional" no está definido
   → IMPACTO: Puede generar scope creep

3. "¿Cómo se maneja calidad del servicio?"
   → ANOTACIÓN: Falta step de validación/quality check
   → IMPACTO: Riesgo de trabajos de baja calidad

PAIN POINTS ACTUALES (As-Is):

1. Pain Point: Múltiples handoffs manuales
   - Descripción: Comercial → Operaciones → Técnico → Administración
   - Impacto: 2-3 días solo en handoffs
   - Frecuencia: 100% de órdenes

2. Pain Point: Presupuesto manual
   - Descripción: Comercial calcula precios en Excel
   - Impacto: Errores, inconsistencias
   - Frecuencia: 100% de órdenes

3. Pain Point: Asignación manual técnico
   - Descripción: Operaciones revisa calendario manualmente
   - Impacto: Subutilización recursos, delays
   - Frecuencia: 100% de órdenes

4. Pain Point: Facturación manual
   - Descripción: Administración genera factura manualmente
   - Impacto: Errores, delays 1-2 días
   - Frecuencia: 100% de órdenes

CONOCIMIENTO TÁCITO CAPTURADO:

- "Siempre presupuestamos 15% más por imprevistos" (Comercial)
- "Los mejores técnicos están siempre llenos" (Operaciones)
- "Los clientes siempre piden cambios en el presupuesto" (Comercial)
- "La documentación del técnico es clave para facturación" (Administración)

EXCEPCIONES IDENTIFICADAS:

1. Emergencia: Cliente necesita servicio inmediato
   - Proceso: Bypass evaluación, asignación directa
   - Responsable: Operaciones (decisión)
   - SLA: 4 horas máximo

2. Trabajo complejo: Requiere múltiples técnicos
   - Proceso: Proyecto separado con planning
   - Responsable: Project Manager
   - SLA: Según proyecto

3. Cliente VIP: Cuenta importante
   - Proceso: Prioridad en asignación
   - Responsable: Gerente Comercial
   - SLA: 50% tiempo normal
```

---

### Fase 4: Optimización (Scope Management)

**El agente define granularidad y perspectivas:**

```
GRANULARIDAD POR ÁREA:

- CLIENTE INTERFACE: Coarse-grained
  - Vista simple, self-service
  - Focus en experiencia usuario

- CALCULADORA PRECIOS: Fine-grained
  - Reglas negocio complejas
  - Múltiples variables

- ASIGNACIÓN TÉCNICOS: Fine-grained
  - Algoritmo optimización
  - Constraints múltiples

- DOCUMENTACIÓN TRABAJO: Medium-grained
  - Estructurada pero flexible
  - Validaciones clave

PERSPECTIVA: TO-BE (Proceso Futuro Optimizado)

DISEÑO OPTIMIZADO:

PASO 1-2: EVALUACIÓN AUTOMATIZADA
👤 Cliente → 📱 Completa → 📝 Formulario inteligente
💻 Sistema → 🤖 Evalúa → 📊 Viabilidad automáticamente
💻 Sistema → 📞 Programa → 📅 Llamada discovery (si necesario)
👥 Comercial → 💬 Discovery → 📋 Identifica necesidades

PASO 3: PRESUPUESTO AUTOMÁTICO
💻 Sistema → 🧮 Calcula → 💰 Precio automáticamente
  ↳ Basado en: tipo trabajo, complejidad, recursos, ubicación
  ↳ Incluye: materiales, horas, margen, descuentos
👥 Comercial → 👀 Revisa → 💰 Precio (ajustes manuales mínimos)
💻 Sistema → 📧 Envía → 💰 Presupuesto dinámico al cliente

PASO 4: APROBACIÓN INSTANTÁNEA
👤 Cliente → ✅ Aprueba → 💰 Un clic
💻 Sistema → 🔄 Convierte → 📅 Orden automáticamente
💻 Sistema → 🎯 Optimiza → 👤 Asignación técnico (IA)

PASO 5: ASIGNACIÓN INTELIGENTE
💻 Sistema → 🤖 Analiza → 🔧 Técnico óptimo
  ↳ Criterios: ubicación, skills, disponibilidad, carga trabajo
💻 Sistema → 📱 Notifica → 👤 Técnico
👤 Técnico → ✅ Confirma → 📅 Acepta orden

PASO 6: EJECUCIÓN CON SOPORTE
👤 Técnico → 🏭 Realiza → 🛠️ Trabajo
💻 Sistema → 📊 Soporte → 📱 Al técnico (historial, manuales)
👤 Técnico → 📝 Documenta → 📱 App móvil (fotos, notas, checklist)

PASO 7: VALIDACIÓN Y CIERRE
👤 Cliente → ✅ Aprueba → 🏭 Trabajo realizado
💻 Sistema → 🔍 Valida → 📝 Documentación completa
💻 Sistema → 📧 Envía → 🧾 Factura automática
👤 Cliente → 💳 Paga → 💳 Online

PASO 8: COBRO AUTOMATIZADO
💻 Sistema → 🔄 Procesa → 💰 Pago
💻 Sistema → 📊 Actualiza → 📈 Métricas
💻 Sistema → 📧 Notifica → 👥 Stakeholders

GAP ANALYSIS: AS-IS vs TO-BE

| Métrica | AS-IS | TO-BE | Mejora |
|---------|-------|-------|--------|
| **Duración Total** | 5-7 días | 4-8 horas | 90% reducción |
| **Handoffs Manuales** | 5 | 1 | 80% reducción |
| **Pasos Automáticos** | 20% | 85% | 325% aumento |
| **Errores** | 15% | 2% | 87% reducción |
| **Satisfacción Cliente** | 6.5/10 | 9/10 | 38% mejora |
| **Productividad Técnico** | 60% | 85% | 42% mejora |

IMPLEMENTACIÓN ROADMAP:

FASE 1 (Mes 1-2): Fundamentos
- ✅ Formulario inteligente
- ✅ Calculadora automática
- ✅ Notificaciones automáticas

FASE 2 (Mes 3-4): Optimización
- ✅ Asignación IA
- ✅ App móvil técnico
- ✅ Integración facturación

FASE 3 (Mes 5-6): Maduración
- ✅ Validación automática
- ✅ Métricas avanzadas
- ✅ AI insights

ROI ESTIMADO:
- Ahorro tiempo: 4.5 días/orden × 500 órdenes/mes = 2,250 días/mes
- Ahorro costos: €50,000/mes en recursos
- Mejora ingresos: +15% satisfacción = +€30,000/mes
- **ROI Total: €80,000/mes vs inversión €100,000 = 80% ROI anual**
```

---

## Output Final del Agente

### Para Ejecutivos:
```
RESUMEN EJECUTIVO - Optimización Órdenes de Trabajo

PROBLEMA ACTUAL:
- Proceso toma 5-7 días
- 5 handoffs manuales
- 15% errores
- Satisfacción: 6.5/10

SOLUCIÓN TO-BE:
- Proceso: 4-8 horas
- 1 handoff manual
- 2% errores
- Satisfacción: 9/10

BENEFICIOS:
- 90% reducción tiempo
- 87% reducción errores
- 38% mejora satisfacción
- ROI: 80% anual

INVERSIÓN: €100,000
AHORRO: €80,000/mes
PAYBACK: 1.25 meses
```

### Para Desarrollo:
```
ESPECIFICACIÓN TÉCNICA - Órdenes de Trabajo

ARQUITECTURA:
- Frontend: Vue 3 + Inertia
- Backend: Laravel 8
- Base de datos: MySQL
- AI: TensorFlow para asignación

APIs REQUERIDAS:
- POST /api/orders (crear orden)
- GET /api/orders/{id} (consultar orden)
- PUT /api/orders/{id}/assign (asignar técnico)
- POST /api/orders/{id}/complete (completar trabajo)

INTEGRACIONES:
- Sistema CRM (clientes)
- ERP (productos/servicios)
- Payment Gateway (pagos)
- SMS/Email service (notificaciones)

VALIDACIONES:
- Formulario: campos obligatorios, formatos
- Presupuesto: rangos permitidos, descuentos
- Asignación: disponibilidad, skills
- Documentación: fotos, notas requeridas
```

### Para Operaciones:
```
GUÍA OPERATIVA - Proceso Optimizado

CAMBIOS PRINCIPALES:
1. Evaluación: Automática (sistema)
2. Presupuesto: Semi-automático (revisión comercial)
3. Asignación: Automática (IA)
4. Facturación: Automática (sistema)

ROLES ACTUALIZADOS:

COMERCIAL:
- Focus en discovery y relación cliente
- Revisión ajustes precios
- Gestión excepciones

OPERACIONES:
- Monitoreo dashboard
- Gestión emergencias
- Ajustes asignación IA

TÉCNICO:
- App móvil simplificada
- Soporte tiempo real
- Documentación estructurada

ADMINISTRACIÓN:
- Excepciones facturación
- Reportes y métricas
- Gestión cobranza

TRAINING REQUERIDO:
- 2 horas: App móvil técnico
- 1 hora: Dashboard operaciones
- 1 hora: Sistema presupuestos
```

---

## Conclusión

Este ejemplo muestra cómo el **Domain Storytelling Master Agent** coordina las 4 skills para:

1. ✅ **Extraer elementos clave** (Pictographic)
2. ✅ **Modelar flujo completo** (Scenario)
3. ✅ **Detectar problemas** (Facilitation)
4. ✅ **Optimizar solución** (Scope)

El resultado es un análisis integral que sirve a múltiples audiencias con diferentes niveles de detalle y propósito.

---

**¿Quieres probar con tu propio proceso?**

```
> Use the domain-storytelling-master agent to analyze [tu proceso aquí]
```
