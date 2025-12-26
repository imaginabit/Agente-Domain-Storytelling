# Ejemplos de Cambio de Granularidad

Este documento contiene casos reales y técnicas para cambiar dinámicamente el nivel de granularidad durante sesiones de Domain Storytelling, adaptándose a las necesidades emergentes y diferentes fases del proyecto.

## ¿Por Qué Cambiar Granularidad?

### Razones Comunes

**1. Propósito evoluciona**
- Empezamos con visión general y necesitamos detalle específico
- Inicialmente detallado pero audiencia necesita overview

**2. Audiencia mixta**
- Equipo con diferentes niveles técnicos
- Diferentes stakeholders con necesidades distintas

**3. Fases del proyecto**
- Descubrimiento: Coarse-grained
- Análisis: Fine-grained
- Diseño: Coarse-grained
- Desarrollo: Fine-grained

**4. Identificación de áreas críticas**
- Ciertos pasos requieren más detalle que otros
- Problemas específicos necesitan profundidad

---

## Caso 1: Cambio Durante Sesión - De Coarse a Fine

### Contexto
**Sesión:** Proceso de facturación
**Audiencia:** Mixto (negocio + desarrollo)
**Fase:** Descubrimiento inicial

#### Inicio: Coarse-Grained (Visión General)

**Tú:** "Empecemos con visión general del proceso de facturación"

**Modelo inicial (coarse):**
```
Proceso de Facturación - Visión General

1. `Técnico completa orden`
2. `Sistema calcula costes`
3. `Administrativo revisa factura`
4. `Factura se envía al cliente`
5. `Cliente paga factura`

Duración: 2-3 días
```

#### Momento de Cambio

**Desarrollador:** "Interesante, pero ¿cómo calcula exactamente los costes el sistema?"

**Tú (detectando necesidad):** "Excelente pregunta. Para el desarrollo, necesitamos más detalle. ¿Podemos profundizar en el cálculo de costes?"

#### Transición a Fine-Grained (Solo para Cálculo)

**Tú:** "Profundicemos en el paso 2 - cálculo de costes"

**Modelo refinado:**
```
Proceso de Facturación - Detalle en Cálculo

1. `Técnico completa orden`
2. `Sistema calcula costes automáticamente`
   2.1. `Consulta tarifa por tipo trabajo`
   2.2. `Multiplica por horas registradas`
   2.3. `Añade coste materiales (precio unitario × cantidad)`
   2.4. `Aplica descuentos cliente (porcentaje)`
   2.5. `Calcula impuestos (según ubicación cliente)`
   2.6. `Suma subtotal + impuestos`
3. `Administrativo revisa factura`
4. `Factura se envía al cliente`
5. `Cliente paga factura`
```

#### Resultado
- Mantiene coarse-grained para proceso general
- Fine-grained solo para área crítica (cálculo)
- Desarrollador tiene detalle suficiente
- Negocio no se abruma con detalles técnicos

---

## Caso 2: Cambio Durante Sesión - De Fine a Coarse

### Contexto
**Sesión:** Proceso de contratación
**Audiencia:** Solo negocio (no técnicos)
**Fase:** Presentación a dirección

#### Inicio: Fine-Grained (Demasiado Detalle)

**Usuario:** "RRHH recibe solicitud, valida formato, verifica campos obligatorios, consulta base de datos de puestos..."

**Tú (observando confusion):** "Interrumpo un momento. Esto es muy detallado para la presentación. ¿Te parece si resumimos a los pasos principales?"

#### Transición a Coarse-Grained

**Tú:** "Para la presentación a dirección, una visión general será más efectiva"

**Modelo resumido:**
```
Proceso de Contratación - Visión General

1. `Necesidad de Personal`
2. `Publicación de Oferta`
3. `Recepción de Candidaturas`
4. `Selección de Candidatos`
5. `Entrevistas`
6. `Selección Finalista`
7. `Contratación`

Duración: 4-6 semanas
```

#### Beneficio del Cambio
- Audiencia (directivos) entiende fácilmente
- Focus en timeline y pasos principales
- Evita perderse en detalles operacionales
- Más efectivo para toma de decisiones

---

## Caso 3: Múltiples Cambios Durante Sesión Larga

### Contexto
**Sesión:** Proceso completo de órdenes (4 horas)
**Audiencia:** Equipo completo (negocio + desarrollo + usuarios)
**Fase:** Workshop integral

#### Estructura de la Sesión

**Fase 1: Visión General (30 min)**
```
Proceso de Órdenes - Overview

1. `Cliente Solicita`
2. `Evaluación y Presupuesto`
3. `Aprobación Cliente`
4. `Asignación Técnico`
5. `Ejecución Servicio`
6. `Facturación`
7. `Cobro`

Duración total: 1-5 días
```

**Fase 2: Profundización Selectiva (2 horas)**

**Tú:** "Ahora profundicemos en las áreas críticas. Empecemos con evaluación y presupuesto"

```
Detalle: Evaluación y Presupuesto

1. `Comercial recibe solicitud`
2. `Comercial agenda llamada discovery`
3. `Comercial realiza llamada`
4. `Comercial identifica necesidades`
5. `Comercial evalúa viabilidad técnica`
6. `Comercial consulta disponibilidad recursos`
7. `Comercial calcula precio`
8. `Comercial prepara presupuesto`
9. `Comercial envía presupuesto`
10. `Cliente revisa presupuesto`
```

**Después de 30 min en esta área:**

**Tú:** "Perfecto, tenemos el detalle de evaluación. Ahora saltamos a ejecución, ¿qué tan detallado necesitan ese proceso?"

**Usuario:** "Para nosotros, con ver los pasos principales está bien"
**Desarrollador:** "Necesitamos detalle para la app móvil"

**Modelo híbrido:**
```
Ejecución Servicio - Detalle Variable

Nivel Usuario (Coarse):
1. `Técnico recibe orden`
2. `Técnico va al lugar`
3. `Técnico realiza trabajo`
4. `Técnico completa orden`

Nivel Desarrollador (Fine):
1.1. `Notificación push a técnico`
1.2. `Técnico confirma recepción`
1.3. `Sistema actualiza status a "EN_CAMINO"`
1.4. `GPS tracking activado`
...
```

**Fase 3: Resumen Ejecutivo (30 min)**

**Tú:** "Para cerrar, volvamos a la visión general pero incorporando lo que aprendimos"

```
Proceso de Órdenes - Versión Final

1. `Cliente Solicita` (vía web/app)
2. `Evaluación y Presupuesto` (automático + revisión manual)
3. `Aprobación Cliente` (digital, instantáneo)
4. `Asignación Técnico` (IA optimiza asignación)
5. `Ejecución Servicio` (con tracking GPS)
6. `Facturación` (automática)
7. `Cobro` (digital)

Duración optimizada: 1-2 días (vs 5 actual)
```

---

## Caso 4: Cambio por Identificación de Problema

### Contexto
**Sesión:** Proceso de solicitud de vacaciones
**Audiencia:** RRHH + desarrollo
**Fase:** Análisis de problemas

#### Inicio: Coarse-Grained Normal

```
Solicitud de Vacaciones

1. `Empleado solicita`
2. `Supervisor aprueba`
3. `Sistema actualiza`
4. `Empleado disfruta`
```

#### Detección de Problema

**Tú:** "¿Y cómo funciona exactamente la aprobación?"

**Usuario:** "Ah, aquí es donde se complica..."

**Cambio a Fine-Grained para Identificar Problema**

```
Detalle: Proceso de Aprobación (Problemático)

2.1. `Empleado completa formulario papel`
2.2. `Empleado lleva formulario a supervisor`
2.3. `Supervisor revisa en su tiempo`
2.4. `Si supervisor disponible: Aprueba/Rechaza`
2.5. `Si supervisor ocupado: Guarda para después`
2.6. `Supervisor escribe respuesta a mano`
2.7. `Supervisor devuelve formulario a empleado`
2.8. `Empleado lleva formulario a RRHH`
2.9. `RRHH actualiza sistema manualmente`
2.10. `RRHH archiva formulario papel`

Duración: 3-5 días (vs 2 horas ideal)
Puntos de fricción: 6 identificados
```

#### Resultado
- Cambio granularidad reveló problemas específicos
- Identificación clara de pain points
- Base para diseño de solución (To-Be)
- Justificación para automatización

---

## Caso 5: Granularidad Adaptativa por Rol

### Contexto
**Sesión:** Proceso de ventas
**Audiencia:** Múltiples roles (comercial, administración, finanzas)
**Fase:** Rediseño de proceso

#### Modelo Granularidad Variable

```
Proceso de Ventas - Por Rol

NIVEL COMERCIAL (Fine-grained para su parte):
1. `Cliente contacta`
2. `Comercial agenda llamada`
3. `Comercial descubre necesidades`
4. `Comercial prepara propuesta`
5. `Comercial presenta propuesta`
6. `Comercial negocia términos`
7. `Comercial cierra venta`

NIVEL ADMINISTRACIÓN (Coarse-grained):
1. `Venta cerrada` → [No necesitan detalles comerciales]
2. `Crear orden`
3. `Enviar a operaciones`
4. `Archivar contrato`

NIVEL FINANZAS (Fine-grained para facturación):
1. `Orden completada`
2. `Facturación automática`
   2.1. `Generar factura`
   2.2. `Validar datos fiscales`
   2.3. `Enviar a cliente`
   2.4. `Registrar en contabilidad`
3. `Seguimiento cobro`
```

#### Ventajas del Modelo
- Cada rol ve su parte en detalle
- Otros roles ven overview de su parte
- Evita información innecesaria
- Enfoque en responsabilidades específicas

---

## Técnicas para Cambios de Granularidad

### Técnica 1: "Zoom In" Selectivo

#### Cuándo Usar
- Audiencia general necesita overview
- Área específica requiere detalle
- Desarrollo/implementación necesita especificidad

#### Proceso
1. **Modelo coarse-grained inicial**
2. **Identifica área que necesita detalle**
3. **Profundiza solo esa área**
4. **Regresa a coarse-grained**

#### Frase de Transición
"Para [propósito], necesitamos más detalle en [área]. ¿Podemos profundizar ahí?"

### Técnica 2: "Zoom Out" Estratégico

#### Cuándo Usar
- Audiencia se pierde en detalles
- Tiempo limitado para presentación
- Nivel técnico inadecuado

#### Proceso
1. **Identifica que audiencia se abruma**
2. **Propón resumir**
3. **Agrupa pasos relacionados**
4. **Mantén información crítica**

#### Frase de Transición
"Para [audiencia], una visión general será más efectiva. ¿Te parece si resumimos?"

### Técnica 3: "Granularidad Híbrida"

#### Cuándo Usar
- Audiencia mixta
- Diferentes áreas requieren diferente detalle
- Presentación a múltiples stakeholders

#### Proceso
1. **Define nivel base** (generalmente coarse)
2. **Identifica áreas críticas** (fine-grained)
3. **Aplica granularidad variable**
4. **Documenta qué nivel para cada parte**

#### Frase de Transición
"Vamos a hacer esto por partes: visión general para todo, pero detalle específico en [área]"

### Técnica 4: "Cambio por Problema"

#### Cuándo Usar
- Se identifica pain point
- Área problemática necesita análisis
- Root cause analysis

#### Proceso
1. **Modelo normal (coarse)**
2. **Detecta problema mencionado**
3. **Cambia a fine-grained**
4. **Analiza problema en detalle**
5. **Regresa a coarse si no hay más problemas**

#### Frase de Transición
"Eso suena problemático. ¿Podemos ver en detalle cómo funciona?"

---

## Manejo de Resistencia al Cambio

### Resistencia: "Esto es demasiado detalle"

#### Estrategias
1. **Justifica por qué:** "Para [propósito], necesitamos este nivel"
2. **Ofrece alternativa:** "¿Prefieres versión resumida ahora y detalle después?"
3. **Limita alcance:** "Solo esta parte específica, no todo el proceso"
4. **Enfoca en beneficio:** "Esto nos ayuda a [beneficio específico]"

#### Ejemplo de Respuesta
"Tiene razón, es detallado. Pero para poder automatizar el cálculo de costes, necesitamos ver exactamente qué hace. ¿Podemos mantener este nivel solo para esa parte?"

### Resistencia: "Esto es demasiado general"

#### Estrategias
1. **Confirma necesidad:** "¿Para qué necesitas más detalle?"
2. **Profundiza selectivamente:** "¿Qué parte específicamente?"
3. **Cambia perspectiva:** "¿Desde qué ángulo necesitas ver?"
4. **Ejemplos concretos:** "¿Un ejemplo ayudaría?"

#### Ejemplo de Respuesta
"Entiendo. ¿Qué parte específicamente necesita más detalle? ¿La validación de datos, el cálculo de precios, o el envío de factura?"

---

## Adaptación por Fases del Proyecto

### Fase 1: Descubrimiento (Coarse-Grained)

**Objetivo:** Entender el dominio
**Granularidad:** Alta (pasos principales)
**Audiencia:** Stakeholders, sponsors

```
Descubrimiento - Visión General

Proceso de [X]:
- [Paso 1]
- [Paso 2]
- [Paso 3]
- [Paso 4]
- [Paso 5]

Duración: [Tiempo]
Actores principales: [Lista]
Sistemas: [Lista]
```

### Fase 2: Análisis (Fine-Grained)

**Objetivo:** Entender problemas y oportunidades
**Granularidad:** Detallada (sub-pasos, validaciones)
**Audiencia:** Analistas, usuarios expertos

```
Análisis - Detalle Operativo

Proceso de [X]:
1. [Paso principal]
   1.1. [Sub-paso]
   1.2. [Sub-paso]
   1.3. [Validación]
2. [Paso principal]
   2.1. [Sub-paso]
   2.2. [Excepción]
...

Pain Points identificados: [Lista]
Oportunidades: [Lista]
```

### Fase 3: Diseño (Coarse + Fine Híbrido)

**Objetivo:** Diseñar solución
**Granularidad:** Fine para solución, coarse para contexto
**Audiencia:** Arquitectos, desarrolladores

```
Diseño - Proceso Futuro

Contexto (Coarse):
Proceso actual: [5 pasos]
Problema: [Pain points]

Solución (Fine):
Proceso futuro optimizado:
1. [Paso detallado]
   1.1. [Sub-paso]
   1.2. [Automatización]
...
```

### Fase 4: Desarrollo (Fine-Grained)

**Objetivo:** Implementar
**Granularidad:** Máxima (especificaciones técnicas)
**Audiencia:** Desarrolladores, QA

```
Desarrollo - Especificación

Proceso optimizado:
[Detalle máximo con validaciones, excepciones, integraciones]

APIs: [Endpoints]
Base de datos: [Esquemas]
Integraciones: [Sistemas]
Testing: [Casos]
```

---

## Errores Comunes en Cambios de Granularidad

### Error 1: Cambiar Sin Comunicar

❌ **Problema:**
```
[Modelando coarse-grained]
[De repente cambia a fine sin avisar]
Usuario: "¿Por qué estamos viendo tanto detalle ahora?"
```

✅ **Solución:**
```
[Modelando coarse-grained]
Tú: "Para el desarrollo, necesitamos más detalle aquí. ¿Podemos profundizar?"
[Cambia a fine-grained]
```

### Error 2: Cambiar Demasiado Frecuentemente

❌ **Problema:**
```
Coarse → Fine → Coarse → Fine → Coarse
[Audiencia confundida, pierde el hilo]
```

✅ **Solución:**
```
Planifica cambios:
1. Coarse inicial (visión)
2. Fine selectivo (áreas críticas)
3. Coarse final (resumen)
```

### Error 3: No Regresar al Nivel Original

❌ **Problema:**
```
Inicia coarse → cambia a fine → se queda en fine
[Pierde vista general]
```

✅ **Solución:**
```
Siempre regresa a nivel original:
1. Coarse inicial
2. Fine específico
3. Regresa a coarse para cerrar
```

### Error 4: Mezclar Granularidades Inconsistente

❌ **Problema:**
```
1. `Cliente solicita` (coarse)
2. `Sistema valida email, verifica base datos, guarda cliente, envía confirmación` (ultra-fine)
3. `Comercial evalúa` (coarse)
```

✅ **Solución:**
```
Consistencia por sección:
1. `Cliente solicita` (coarse)
2. `Sistema procesa solicitud` (coarse que incluye validación)
   2.1. [Si necesitan detalle: sub-pasos]
3. `Comercial evalúa` (coarse)
```

---

## Plantillas para Cambios

### Template: Zoom In

```
PROPUESTA DE CAMBIO:

"Para [propósito específico], necesitamos más detalle en [área].
¿Podemos profundizar en esa parte?"

ÁREA A PROFUNDIZAR:
[Descripción del área]

NIVEL ACTUAL:
[Paso actual]

NIVEL PROPUESTO:
[Sub-pasos detallados]

DURACIÓN ESTIMADA:
[Tiempo para esta parte]

REGRESO A NIVEL ORIGINAL:
"Perfecto, tenemos el detalle necesario.
Regresamos a visión general para [siguiente parte]."
```

### Template: Zoom Out

```
PROPUESTA DE CAMBIO:

"Para [audiencia], una visión general será más efectiva.
¿Te parece si resumimos a los pasos principales?"

ÁREA A RESUMIR:
[Descripción del área]

NIVEL ACTUAL:
[Sub-pasos detallados]

NIVEL PROPUESTO:
[Pasos agrupados]

MANTENER INFORMACIÓN CRÍTICA:
[Qué no se debe perder]

OPCIONAL:
"Podemos mantener este nivel o ir más profundo si es necesario."
```

### Template: Híbrido

```
PROPUESTA DE CAMBIO:

"Hagamos granularidad variable: visión general para todo,
pero detalle específico en [áreas críticas]."

ESTRUCTURA:
- Nivel base: [Coarse/Fine]
- Áreas críticas: [Fine/Coarse]
- Regreso a nivel base: [Para cerrar]

ÁREAS CON DETALLE:
1. [Área 1] - Razón: [Por qué necesita detalle]
2. [Área 2] - Razón: [Por qué necesita detalle]

ÁREAS CON OVERVIEW:
1. [Área 1] - Razón: [Suficiente con visión general]
2. [Área 2] - Razón: [Suficiente con visión general]
```

---

## Resumen: Cambio de Granularidad

### Principios Clave

1. **Comunicar cambios** - Siempre avisar antes de cambiar
2. **Justificar por qué** - Explicar necesidad del cambio
3. **Planificar estructura** - Coarse → Fine → Coarse
4. **Regresar al nivel** - No quedarse en fine
5. **Adaptar a audiencia** - Nivel apropiado para cada uno

### Señales para Cambiar

**Cambiar a Fine:**
- "¿Cómo funciona exactamente?"
- Necesidad de implementar
- Identificación de problemas
- Área crítica identificada

**Cambiar a Coarse:**
- Audiencia se pierde
- Demasiado tiempo en detalles
- Presentación a no técnicos
- Nivel técnico inadecuado

### Estructura Recomendada

1. **Inicio:** Coarse-grained (visión general)
2. **Desarrollo:** Fine-grained selectivo (áreas críticas)
3. **Cierre:** Coarse-grained (resumen con insights)

### Frases de Transición

**Para profundizar:**
- "Para [propósito], necesitamos más detalle en [área]"
- "¿Podemos ver en detalle cómo funciona [X]?"
- "Eso suena crítico, ¿qué pasa exactamente?"

**Para resumir:**
- "Para [audiencia], una visión general será más efectiva"
- "¿Te parece si mantenemos los pasos principales?"
- "Evitemos perderse en detalles técnicos"

**Recuerda:** El cambio de granularidad es una herramienta, no una meta. Úsala estratégicamente para servir mejor a la audiencia y al propósito.
