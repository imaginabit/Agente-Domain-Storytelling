# Gestión de Expectativas

Este documento contiene técnicas y estrategias para manejar expectativas de stakeholders sobre el nivel de granularidad, perspectiva temporal y alcance del modelado, asegurando que todos estén alineados y satisfechos con el resultado.

## Importancia de Gestionar Expectativas

### Problemas sin Gestión de Expectativas

❌ **Desalineación** - Cada uno espera algo diferente
❌ **Scope creep** - "Mientras estamos, hagamos también..."
❌ **Frustración** - "Esto no es lo que necesitaba"
❌ **Tiempo excesivo** - Demasiado detalle para el propósito
❌ **Re-trabajo** - Hacerlo otra vez con scope correcto

### Beneficios de Gestión Adecuada

✅ **Alineación** - Todos quieren lo mismo
✅ **Eficiencia** - Tiempo bien utilizado
✅ **Satisfacción** - Resultado cumple expectativas
✅ **Focus** - Sin distractions
✅ **Entrega efectiva** - Modelo usado como se planeó

---

## Expectativas Comunes por Stakeholder

### Ejecutivos/Directivos

#### Expectativas Típicas
- **Tiempo:** 30-60 minutos máximo
- **Granularidad:** Coarse-grained (visión general)
- **Perspectiva:** As-Is + To-Be (problema + solución)
- **Output:** Dashboard, ROI, beneficios
- **Decisión:** Aprobar/invertir/no invertir

#### Señales de Desalineación
- "¿Pero cómo funciona exactamente?" → Quiere más detalle técnico
- "¿Y el código?" → Mezclando niveles
- "¿Qué pasa si falla X?" → Enfoque en excepciones
- "¿Y si el proveedor no responde?" → Casos edge

#### Estrategias de Alineación
1. **Clarificar propósito:** "Para una decisión ejecutiva, no necesitamos el cómo técnico"
2. **Enfocar en valor:** "¿Le interesa más el ROI o la implementación?"
3. **Ofrecer detalles aparte:** "Si quiere detalles técnicos, podemos hacerlo en sesión separada"
4. **Usar analogías:** "Es como un mapa de autopistas vs. calles específicas"

### Desarrolladores/Técnicos

#### Expectativas Típicas
- **Tiempo:** 2-4 horas (sesión completa)
- **Granularidad:** Fine-grained (detalles técnicos)
- **Perspectiva:** To-Be (proceso futuro para implementar)
- **Output:** Especificaciones, APIs, arquitectura
- **Decisión:** Cómo implementar, estimar esfuerzo

#### Señales de Desalineación
- "Esto es muy de alto nivel" → Necesita más detalle
- "¿Y la base de datos?" → Quiere especificaciones técnicas
- "¿Qué pasa si...?" → Explorando casos edge
- "Falta integración con..." → Pensando en implementaciones

#### Estrategias de Alineación
1. **Confirmar nivel:** "¿Necesita ver cada validación y excepción?"
2. **Profundizar apropiadamente:** "Para desarrollo, necesitamos detalle técnico"
3. **Manejar edge cases:** "¿Exploramos casos especiales o nos enfocamos en el happy path?"
4. **Documentar decisiones:** "Anotamos que [decisión técnica] para sesión aparte"

### Usuarios Finales

#### Expectativas Típicas
- **Tiempo:** 1-2 horas (con breaks)
- **Granularidad:** Fine-grained en su área
- **Perspectiva:** As-Is (cómo funciona ahora) + mejoras en su trabajo
- **Output:** Guía de su trabajo, beneficios claros
- **Decisión:** Cómo haré mi trabajo mejor

#### Señales de Desalineación
- "Esto no es lo que hago" → Área de trabajo mal definida
- "¿Y si no sé usar el sistema?" → Preocupación por adopción
- "¿Qué pasa si...?" → Explorando problemas
- "Eso no es realista" → Expectativa de To-Be vs. realidad

#### Estrategias de Alineación
1. **Definir su rol:** "Nos enfocamos en tu trabajo, ¿correcto?"
2. **Mostrar beneficios:** "¿Cómo te beneficia este cambio?"
3. **Validar proceso:** "¿Esto refleja cómo lo haces?"
4. **Abordar concerns:** "¿Qué te preocupa del cambio?"

### Stakeholders/Clientes

#### Expectativas Típicas
- **Tiempo:** 15-30 minutos (presentación)
- **Granularidad:** Coarse-grained (cambios que notarán)
- **Perspectiva:** To-Be (experiencia mejorada)
- **Output:** Timeline, cambios, beneficios
- **Decisión:** Aceptar/no aceptar, feedback

#### Señales de Desalineación
- "¿Cómo funciona internamente?" → Detalles técnicos no relevantes
- "¿Y si hay problemas?" → Enfoque en riesgos
- "¿Cuándo estará listo?" → Timeline más importante que proceso
- "¿Es más complicado?" → Preocupación por usabilidad

#### Estrategias de Alineación
1. **Enfocar en experiencia:** "¿Qué cambia para ti?"
2. **Simplificar:** "No necesita saber cómo funciona internamente"
3. **Timeline claro:** "¿Le interesa más cuándo o cómo?"
4. **Minimizar fricción:** "¿Será más fácil o más complicado?"

---

## Técnicas de Gestión de Expectativas

### Técnica 1: Alinear al Inicio (Critical)

#### Proceso
1. **Define scope claramente**
2. **Confirma con stakeholders**
3. **Documenta expectativas**
4. **Obtiene acuerdo**

#### Script de Alineación

**Tú (al inicio de sesión):**
"Antes de empezar, queremos alinear expectativas:

**Propósito:** [Qué buscamos lograr]
**Audiencia:** [Para quién es esto]
**Granularidad:** [Visión general / Detalle paso a paso]
**Perspectiva:** [Proceso actual / Proceso futuro / Ambos]
**Duración estimada:** [Tiempo]
**Output esperado:** [Qué van a recibir]

¿Esto refleja lo que necesitan? ¿Algo que agregar o cambiar?"

#### Ejemplo Completado

**Tú:**
"Para esta sesión:
- **Propósito:** Diseñar proceso de vacaciones optimizado
- **Audiencia:** RRHH + desarrollo
- **Granularidad:** Visión general para RRHH, detalle técnico para desarrollo
- **Perspectiva:** Proceso futuro (To-Be)
- **Duración:** 90 minutos
- **Output:** Especificación para desarrollo + guía para RRHH

¿Esto es correcto? ¿Algo que ajustar?"

### Técnica 2: Reforzar Durante Sesión

#### Proceso
1. **Recuerda scope cuando sea necesario**
2. **Redirecciona desviaciones**
3. **Propón sesiones separadas para temas adicionales**

#### Frases de Refuerzo

**Cuando scope creep:**
"Eso es importante, pero está fuera del scope de esta sesión. ¿Lo anotamos para sesión aparte?"

**Cuando piden nivel diferente:**
"Para [propósito], [nivel actual] es apropiado. ¿Quiere que hagamos una versión [otro nivel] también?"

**Cuando mezclan perspectivas:**
"¿Estamos documentando cómo es ahora o cómo debería ser? Una cosa a la vez"

### Técnica 3: Manejo de Desviaciones

#### Desviación 1: Piden Demasiado Detalle

**Situación:**
Usuario pide "pero ¿cómo funciona exactamente el sistema de validación?"

**Respuesta Estratégica:**
"Excelente pregunta. Para [propósito actual], no necesitamos ese nivel técnico. ¿Le parece si:
1. Mantenemos visión general para esta sesión
2. Si después necesita detalles de implementación, hacemos sesión técnica específica?

Así aprovechamos el tiempo para [objetivo actual]."

#### Desviación 2: Piden Muy Poco Detalle

**Situación:**
Desarrollador dice "está bien, entiendo el proceso"

**Respuesta Estratégica:**
"Me alegra que tenga claridad. Para asegurarnos que podemos implementarlo correctamente, ¿podemos profundizar un poco en [área específica]? Especialmente en [validaciones/excepciones/integraciones]."

#### Desviación 3: Mezclan As-Is y To-Be

**Situación:**
Usuario: "Ahora tenemos que ir a RRHH, pero idealmente sería automático"

**Respuesta Estratégica:**
"Interrumpo un momento. ¿Estamos documentando el proceso actual (As-Is) o diseñando el futuro (To-Be)?

Si documentamos el actual: vemos cómo es ahora, incluyendo 'ir a RRHH'
Si diseñamos el futuro: asumimos que ya es automático

¿Cuál prefiere que hagamos primero?"

### Técnica 4: Manejo de Scope Creep

#### Scope Creep Tipo 1: "Mientras estamos..."

**Usuario:** "Mientras estamos con el proceso de vacaciones, ¿podemos ver también el proceso de bajas?"

**Respuesta:**
"Es tentador, pero para mantener el foco y no extendernos, ¿qué le parece si:
1. Terminamos vacaciones hoy
2. Programamos sesión separada para bajas la próxima semana?

Así le damos la atención que merece cada proceso."

#### Scope Creep Tipo 2: "Y también esto..."

**Usuario:** "Ah, y también el proceso de formación, y el de evaluaciones..."

**Respuesta:**
"Veo varios procesos relacionados. Para no abarcar demasiado y perdernos, ¿podemos priorizar? ¿Cuál es el más urgente o crítico? Empezamos por ahí y luego continuamos con los otros."

### Técnica 5: Manejo de Expectativas No Realistas

#### Expectativa 1: "Esto debe ser perfecto desde el inicio"

**Situación:**
Usuario: "El modelo debe capturar todo, cada detalle, cada excepción"

**Respuesta:**
"Entiendo que quiere completitud. En Domain Storytelling, empezamos con el happy path (80% de casos) y luego agregamos variaciones. ¿Le parece si:
1. Capturamos el proceso principal primero
2. Luego documentamos excepciones como anotaciones
3. Iteramos para agregar detalles?

Así evitamos que se vuelva abrumador desde el inicio."

#### Expectativa 2: "Todo debe ser automático en el futuro"

**Situación:**
Usuario: "En el futuro, esto debería ser 100% automático"

**Respuesta:**
"Esa es una visión ambiciosa. Para que sea realista y alcanzable, ¿podemos priorizar qué automatizamos primero? Normalmente:
1. Automatizamos lo más repetitivo
2. Lo que tiene mayor ROI
3. Lo que es técnicamente factible

¿Cuál sería su top 3 para automatizar?"

---

## Scripts para Situaciones Específicas

### Script: Audiencia Mixta

**Situación:** Sesión con técnicos y negocio

**Tú:**
"Tenemos audiencia mixta. Propongo:
1. Empezamos con visión general (para todos)
2. Profundizamos en áreas críticas (según audiencia)
3. Terminamos con resumen ejecutivo (para todos)

¿Les parece bien esta estructura?"

**Durante sesión:**
- "Para esta parte técnica, [desarrolladores] ¿necesitan más detalle?"
- "Para esta parte de negocio, [stakeholders] ¿está claro?"

### Script: Primera Vez con Domain Storytelling

**Situación:** Audiencia no conoce la metodología

**Tú:**
"Domain Storytelling es una técnica para capturar procesos de forma colaborativa. Funciona así:
1. Ustedes narran su proceso
2. Identificamos el 'happy path' (80% casos)
3. Capturamos variaciones como anotaciones
4. Refinamos hasta tener modelo claro

Es iterativo, no tiene que ser perfecto desde el inicio. ¿Alguna pregunta antes de empezar?"

### Script: Sesión Muy Larga (más de 2 horas)

**Situación:** Sesión se extiende

**Tú:**
"Llevamos [tiempo]. Para no fatigar a todos, ¿qué prefiere?
1. Hacer break de 15 minutos y continuar
2. Pausar aquí y continuar en sesión separada
3. Resumir lo que tenemos y programar seguimiento

¿Cuál le funciona mejor?"

### Script: Stakeholder Se Sale de Scope

**Situación:** Participante lleva la conversación a tema no relacionado

**Tú:**
"[Nombre], esa es una observación valiosa. La anotamos para el proyecto [correspondiente], pero para mantener el foco en [proceso actual], ¿podemos continuar con [tema]?

No queremos perder el hilo de lo que estamos modelando."

---

## Herramientas de Alineación

### Checklist de Expectativas (Pre-Sesión)

```
SESIÓN: [Nombre del proceso]
FECHA: [Fecha]
PARTICIPANTES: [Lista]

EXPECTATIVAS ALINEADAS:
□ Propósito definido y acordado
□ Granularidad acordada (coarse/fine/híbrida)
□ Perspectiva acordada (As-Is/To-Be/híbrida)
□ Duración estimada acordada
□ Output esperado definido
□ Scope boundaries claros
□ Rollos de participantes claros
□ Expectativas no realistas abordadas
□ Plan B definido (si algo no funciona)
```

### Contrato de Sesión

```
CONTRATO DE SESIÓN - [Proceso]

PROPÓSITO:
[Qué queremos lograr]

SCOPE:
✓ INCLUIDO: [Lista]
✗ EXCLUIDO: [Lista]

NIVEL DE DETALLE:
- [Área 1]: [Coarse/Fine]
- [Área 2]: [Coarse/Fine]

PERSPECTIVA:
- [Proceso actual/futuro/híbrido]

OUTPUT:
[Qué van a recibir]

DURACIÓN:
[Tiempo estimado]

REGLAS:
1. [Regla 1]
2. [Regla 2]

FIRMAS:
[Participantes confirman entendimiento]
```

### Matriz de Expectativas

| Stakeholder | Expectativa | Alineación | Acción |
|-------------|-------------|------------|--------|
| [Nombre] | [Qué espera] | [Sí/No/Parcial] | [Si no alineado] |
| [Nombre] | [Qué espera] | [Sí/No/Parcial] | [Si no alineado] |

---

## Manejo de Conflictos

### Conflicto 1: Granularidad Diferente

**Situación:**
Negocio: "Esto es demasiado técnico"
Desarrollo: "Esto es demasiado general"

**Resolución:**
"Hemos identificado que tenemos necesidades diferentes. Propongo:
1. Modelamos versión coarse-grained para negocio
2. Modelamos versión fine-grained para desarrollo
3. Ambas basadas en el mismo proceso base
4. Sesión de mapeo para asegurar consistencia

¿Les parece bien esta aproximación?"

### Conflicto 2: Perspectiva Temporal

**Situación:**
Usuario: "Documentemos cómo es ahora"
Ejecutivo: "Diseñemos cómo debería ser"

**Resolución:**
"Temos dos necesidades válidas. Propongo:
1. Primero As-Is (30 min) - para entender situación actual
2. Luego To-Be (60 min) - para diseñar solución
3. Comparación (15 min) - para ver gap
4. Priorización (15 min) - para roadmap

Así tenemos ambos y sabemos qué cambiar. ¿Les parece bien?"

### Conflicto 3: Scope Demasiado Amplio

**Situación:**
Múltiples stakeholders quieren incluir sus procesos

**Resolución:**
"Entiendo que varios procesos son importantes. Para no abarcar demasiado y perder calidad, propongo:
1. Priorizar procesos (top 3)
2. Hacer bien uno antes de pasar al siguiente
3. Roadmap de sesiones

¿Cuál sería el proceso más crítico para empezar?"

---

## Seguimiento Post-Sesión

### Validación de Expectativas

**24 horas después:**
"Gracias por la sesión de [proceso]. Para asegurar que entregamos lo que necesitan:

1. ¿El modelo refleja sus expectativas?
2. ¿El nivel de detalle es apropiado?
3. ¿La perspectiva (As-Is/To-Be) es correcta?
4. ¿Algo que necesiten agregar o ajustar?

Si todo está bien, procedemos a [siguiente paso]. Si hay ajustes, los incorporamos."

### Manejo de Feedback

**Feedback Positivo:**
"Excelente que el modelo cumpla expectativas. ¿Podemos usar esto como base para [siguiente fase]?"

**Feedback Negativo - No cumple expectativas:**
"Entiendo que no cumple lo que esperaban. ¿Qué específicamente no está bien? ¿Es:
- El nivel de detalle (demasiado/muy poco)?
- La perspectiva (actual vs. futuro)?
- El scope (incluye/excluye algo)?

Podemos ajustarlo para que sí cumpla sus expectativas."

---

## Errores Comunes en Gestión de Expectativas

### Error 1: No Alinear al Inicio

❌ **Problema:**
```
Tú: "Cuéntame sobre el proceso"
[Asume coarse-grained]
Usuario: [Narra en detalle técnico]
[30 minutos después]
Usuario: "Esto no es lo que necesitaba"
```

✅ **Solución:**
```
Tú: "Antes de empezar, ¿queremos visión general o detalle paso a paso?"
```

### Error 2: No Documentar Acuerdo

❌ **Problema:**
```
Alineación verbal pero no documentada
```

✅ **Solución:**
```
Enviar confirmación post-sesión:
"Resumen de nuestra sesión:
- Scope: [Definición]
- Granularidad: [Nivel]
- Output: [Entregable]
¿Correcto?"
```

### Error 3: Ser Inflexible

❌ **Problema:**
```
"Solo hacemos coarse-grained, no cambiamos"
[Usuario frustrado]
```

✅ **Solución:**
```
"Podemos ajustar el scope durante la sesión si es necesario.
Lo importante es que sirva a su propósito."
```

### Error 4: No Abordar Expectativas No Realistas

❌ **Problema:**
```
Usuario: "Debe capturar todo perfectamente"
Tú: "Perfecto"
[Imposible de cumplir]
```

✅ **Solución:**
```
"Para ser realistas, Domain Storytelling funciona mejor
cuando empezamos con el happy path y luego agregamos detalles.
¿Podemos estructurarlo así?"
```

---

## Resumen: Gestión de Expectativas

### Principios Clave

1. **Alinear al inicio** - 5 minutos de alineación ahorran 1 hora de re-trabajo
2. **Documentar acuerdos** - Verbal no es suficiente
3. **Ser flexible** - Adaptar según feedback
4. **Priorizar** - No todo puede estar en una sesión
5. **Comunicar cambios** - Avisar cuando scope cambia

### Expectativas Típicas

| Stakeholder | Granularidad | Perspectiva | Duración |
|-------------|--------------|-------------|----------|
| **Ejecutivos** | Coarse | Híbrido | 30-60 min |
| **Desarrolladores** | Fine | To-Be | 2-4 horas |
| **Usuarios** | Fine (su área) | As-Is + To-Be | 1-2 horas |
| **Stakeholders** | Coarse | To-Be | 15-30 min |

### Frases Clave

**Para alinear:**
"Antes de empezar, queremos alinear expectativas..."
"¿Esto refleja lo que necesitan?"

**Para reforzar:**
"Para [propósito], [nivel] es apropiado..."
"Eso está fuera del scope, lo anotamos para después..."

**Para manejar conflictos:**
"Tenemos necesidades diferentes, propongo..."
"¿Podemos priorizar? Empezamos por..."

**Recuerda:** La gestión de expectativas no es una técnica más, es la base del éxito. Una sesión bien alineada desde el inicio ahorra tiempo, evita frustraciones y entrega valor real.
