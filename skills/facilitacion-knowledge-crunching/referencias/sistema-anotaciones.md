# Sistema de Anotaciones

Este documento define un sistema completo para registrar variaciones, errores, asunciones y pain points sin complicar la narrativa principal del happy path, manteniendo la historia limpia mientras se captura toda la complejidad del dominio.

## ¿Por qué usar Anotaciones?

### Problemas sin Sistema de Anotaciones

❌ **Historia principal se complica** - Se mezclan happy path con variaciones
❌ **Difícil de seguir** - El lector pierde el hilo principal
❌ **Imposible de implementar incrementalmente** - Todo debe hacerse junto
❌ **Feedback delayed** - No se puede validar el flujo principal
❌ **Complejidad abrumadora** - Demasiada información de golpe

### Beneficios del Sistema de Anotaciones

✅ **Historia principal limpia** - Solo el happy path
✅ **Fácil de implementar** - Empezar por lo simple
✅ **Variaciones organizadas** - Cada una documentada y clasificada
✅ **Progressive disclosure** - Mostrar complejidad gradualmente
✅ **Feedback temprano** - Validar base antes de variaciones
✅ **Flexible** - Agregar complejidad cuando sea necesario

---

## Principios del Sistema

### 1. Separación Clara
**Historia principal** = Happy path (80% casos)
**Anotaciones** = Todo lo demás (variaciones, errores, asunciones, pain points)

### 2. Referencias Cruzadas
Cada anotación debe indicar **dónde** aparece en la historia principal
```
[ANOTACIÓN] Contexto: Paso 3 (validación de documentos)
```

### 3. Clasificación Consistente
Cada anotación tiene un **tipo** y **código único**
```
[V1] Variación - Cliente premium
[E2] Error - Sistema caído
[P1] Pain point - Impresora rota
```

### 4. Formato Estándar
Todas las anotaciones siguen el mismo formato para facilitar lectura

### 5. Priorización
Las anotaciones se clasifican por **frecuencia**, **impacto** y **complejidad**

---

## Tipos de Anotaciones

### V: Variaciones de Flujo

**Definición:** Flujos alternativos que divergen del happy path

**Características:**
- Cambian la secuencia de pasos
- Toman ruta diferente en algún punto
- Pueden reconectarse con el flujo principal

**Ejemplos:**
- "Si es cliente premium, saltamos aprobación"
- "Cuando hay emergencia, priorizamos"
- "Para clientes nuevos, proceso extra de verificación"

**Formato:**
```
Vx: [Nombre descriptivo]
Frecuencia: [%]
Diverge en: Paso [X]
Reconecta en: Paso [Y] / No reconecta
Descripción: [Qué cambia]
Prioridad: [H/M/B]
```

**Ejemplo completo:**
```
V1: Cliente premium
Frecuencia: 20%
Diverge en: Paso 4 (aprobar solicitud)
Reconecta en: Paso 6 (enviar confirmación)
Descripción: Clientes premium no requieren aprobación manual, se auto-aprueban
Prioridad: Alta
```

---

### E: Errores y Excepciones

**Definición:** Casos excepcionales cuando algo falla o sale mal

**Características:**
- Ocurren cuando algo no funciona como esperado
- Requieren manejo especial
- Pueden ser errores del sistema, humanos o externos

**Ejemplos:**
- "Si el sistema falla, usar proceso manual"
- "Si el cliente rechaza, ofrecer alternativa"
- "Si no hay stock, cancelar orden"

**Formato:**
```
Ex: [Tipo de error]
Contexto: Paso [X]
Trigger: [Qué lo causa]
Manejo: [Qué se hace]
Impacto: [Bajo/Medio/Alto]
```

**Ejemplo completo:**
```
E1: Sistema de facturación caído
Contexto: Paso 5 (generar factura)
Trigger: Sistema no responde
Manejo: Usar plantilla de emergencia y generar manualmente
Impacto: Alto - retrasa facturación
```

---

### A: Asunciones

**Definición:** Cosas que se dan por sentado pero no son explícitas

**Características:**
- "Conocimiento común" que todos conocen
- Reglas no escritas
- Dependencias implícitas

**Ejemplos:**
- "Asumimos que siempre hay stock"
- "El supervisor siempre está disponible"
- "El cliente responde en 24h"

**Formato:**
```
Ax: [Descripción de asunción]
Contexto: [General/Paso X]
Asunción: [Qué se asume]
Riesgo: [Qué pasa si no se cumple]
Validación: [Cómo verificar]
```

**Ejemplo completo:**
```
A1: Disponibilidad del supervisor
Contexto: Paso 3 (aprobar solicitudes)
Asunción: El supervisor está disponible para aprobar en <2 horas
Riesgo: Si supervisor no disponible, solicitudes se retrasan
Validación: Verificar carga de trabajo del supervisor
```

---

### P: Pain Points (Puntos de Dolor)

**Definición:** Pasos problemáticos donde hay ineficiencias o frustraciones

**Características:**
- Causan demoras o errores
- Generan frustración en usuarios
- Pueden requerir workarounds

**Ejemplos:**
- "La impresora siempre está rota"
- "Copiar datos entre sistemas es tedioso"
- "El sistema es muy lento aquí"

**Formato:**
```
Px: [Descripción del problema]
Contexto: Paso [X]
Síntoma: [Qué se observa]
Frecuencia: [%]
Tiempo perdido: [Cuánto tiempo]
Impacto: [Bajo/Medio/Alto]
Workaround: [Cómo lo resuelven ahora]
```

**Ejemplo completo:**
```
P1: Transcripción manual entre sistemas
Contexto: Pasos 3-5 (sincronizar datos tablet-sistema)
Síntoma: Errores al copiar datos manualmente
Frecuencia: 30%
Tiempo perdido: 10-15 minutos por transacción
Impacto: Alto - errores de cálculo
Workaround: Doble verificación manual
```

---

### Q: Preguntas/Gaps

**Definición:** Cosas que no están claras o necesitan clarificación

**Características:**
- Información faltante
- Inconsistencias detectadas
- Aspectos que necesitan validación

**Ejemplos:**
- "¿Cómo se calcula el descuento?"
- "¿Qué pasa si el cliente no responde?"
- "Inconsistencia entre paso 2 y 5"

**Formato:**
```
Qx: [Descripción de la pregunta]
Contexto: Paso [X]
Pregunta: [Pregunta específica]
Respuesta esperada: [Qué queremos saber]
Estado: [Pendiente/Resuelta/Validar con experto]
```

**Ejemplo completo:**
```
Q1: Cálculo de descuentos
Contexto: Paso 4 (calcular precio)
Pregunta: ¿Cómo se determina qué descuentos aplicar? ¿Hay reglas?
Respuesta esperada: Criterios específicos de aplicación de descuentos
Estado: Pendiente - necesita clarificación con experto
```

---

### I: Información Adicional

**Definición:** Datos útiles que no caben en la historia principal

**Características:**
- Contexto adicional
- Detalles que enriquecen entendimiento
- No afectan el flujo principal

**Ejemplos:**
- "El email incluye PDF y enlace de tracking"
- "Los datos se guardan automáticamente cada 30 segundos"
- "El supervisor puede aprobar hasta 1000€ sin escalación"

**Formato:**
```
Ix: [Descripción]
Contexto: [General/Paso X]
Información: [Qué se agrega]
Utilidad: [Por qué es útil saberlo]
```

**Ejemplo completo:**
```
I1: Métodos de envío de órdenes
Contexto: Paso 6 (enviar orden)
Información: 70% email + PDF, 30% portal web (manual)
Utilidad: Entender mix de canales para futuras integraciones
```

---

## Formato Estándar de Anotaciones

### Template Completo

```
[TIPO][ID]: [Nombre descriptivo]

CONTEXTO:
- Historia principal: [Nombre de historia]
- Paso donde aparece: [Paso X]
- Porcentaje de casos: [%] (si aplica)

DESCRIPCIÓN:
[Explicación detallada de la anotación]

DETALLES:
[Información específica según el tipo]

PRIORIDAD:
- Frecuencia: [Alta/Media/Baja]
- Impacto: [Alto/Medio/Bajo]
- Complejidad: [Alta/Media/Baja]
- Implementación: [Alta/Media/Baja]

ESTADO:
- [Pendiente/En progreso/Completa]
- [Fecha de creación]
- [Responsable (si aplica)]

NOTAS:
[Observaciones adicionales, dependencias, etc.]
```

### Template Simplificado

```
[TIPO][ID]: [Título]
Contexto: Paso [X] | Frecuencia: [%]
Descripción: [1-2 líneas]
Prioridad: [H/M/B]
Estado: [Pendiente/Completa]
```

---

## Sistema de Codificación

### Prefijos por Tipo

- **V** - Variación de flujo
- **E** - Error/Excepción
- **A** - Asunción
- **P** - Pain Point
- **Q** - Pregunta/Gap
- **I** - Información adicional

### Estructura del Código

```
[TIPO][NÚMERO]: [Nombre corto]
Ejemplos:
V1, V2, V3... (Variaciones 1, 2, 3...)
E1, E2, E3... (Errores 1, 2, 3...)
P1, P2... (Pain points 1, 2...)
```

### Convenciones de Nomenclatura

**Variaciones:**
```
V1: Cliente premium
V2: Urgente
V3: Cliente nuevo
```

**Errores:**
```
E1: Sistema caído
E2: Datos inválidos
E3: Cliente no disponible
```

**Pain Points:**
```
P1: Transcripción manual
P2: Impresora rota
P3: Sistema lento
```

---

## Ejemplos Completos de Sistema

### Ejemplo 1: Proceso de Facturación

#### Historia Principal (Happy Path)
```
1. `Técnico completa orden`
2. `Técnico genera parte`
3. `Sistema calcula costes`
4. `Administrativo crea factura`
5. `Administrativo envía factura`
6. `Cliente recibe factura`
7. `Cliente paga factura`
```

#### Anotaciones Registradas

```
V1: Factura > 1000€
Contexto: Paso 4 (crear factura)
Frecuencia: 30%
Diverge: Paso 4.1 - Solicita aprobación director
Reconecta: Paso 4 (continuar crear factura)
Descripción: Facturas >1000€ requieren aprobación manual del director
Prioridad: Alta

E1: Cliente no responde
Contexto: Paso 6 (cliente recibe factura)
Frecuencia: 25%
Trigger: Cliente no responde en 15 días
Manejo: Sistema envía recordatorio automático
Impacto: Medio - retrasa cobro
Prioridad: Media

A1: Cliente siempre tiene datos actualizados
Contexto: General
Asunción: Los datos fiscales del cliente están correctos
Riesgo: Si datos incorrectos, factura inválida
Validación: Verificar datos cada 6 meses
Prioridad: Alta

P1: Calcular costes manualmente
Contexto: Paso 3 (calcular costes)
Síntoma: "A veces tenemos que calcular algunos costes a mano"
Frecuencia: 15%
Tiempo perdido: 5-10 minutos por factura
Impacto: Medio - errores potenciales
Workaround: Calculadora y verificación manual
Prioridad: Media

Q1: Criterios de cálculo de impuestos
Contexto: Paso 3 (calcular costes)
Pregunta: ¿Qué reglas se usan para calcular impuestos? ¿Cambian por tipo de cliente?
Respuesta esperada: Tabla de impuestos por categoría
Estado: Pendiente
```

---

### Ejemplo 2: Proceso de Contratación

#### Historia Principal (Happy Path)
```
1. `RRHH identifica necesidad`
2. `RRHH publica oferta`
3. `Candidatos envían CVs`
4. `Recruiter revisa CVs`
5. `Recruiter selecciona candidatos`
6. `RRHH programa entrevistas`
7. `Candidatos asisten entrevistas`
8. `RRHH selecciona finalista`
9. `RRHH prepara contrato`
10. `Candidato firma contrato`
11. `RRHH registra empleado`
```

#### Anotaciones Registradas

```
V1: Urgente
Contexto: Paso 1 (identificar necesidad)
Frecuencia: 20%
Diverge: Paso 1.1 - Marcada como urgente
Reconecta: Paso 2 (publicar con alta prioridad)
Descripción: Posiciones urgentes van a portales premium y headhunters
Prioridad: Alta

V2: Candidatos referidos
Contexto: Paso 3 (candidatos envían CVs)
Frecuencia: 15%
Diverge: Paso 2.1 - Candidatos referidos跳过 revisión inicial
Reconecta: Paso 4 (revisión directa)
Descripción: Empleados pueden referir candidatos que van directo a entrevista
Prioridad: Alta

E1: No hay candidatos válidos
Contexto: Paso 5 (seleccionar candidatos)
Frecuencia: 10%
Trigger: Ningún candidato cumple criterios
Manejo: RRHH republica oferta con criterios ajustados
Impacto: Alto - retrasa contratación
Prioridad: Alta

A1: Siempre hay candidatos suficientes
Contexto: General
Asunción: Habrá candidatos válidos en 2-4 semanas
Riesgo: Si no hay candidatos, proceso se alarga
Validación: Revisar histórico de tiempo de cobertura
Prioridad: Media

P1: Revisión manual de CVs
Contexto: Paso 4 (revisar CVs)
Síntoma: "Es muy tedioso revisar 50+ CVs para una posición"
Frecuencia: 80%
Tiempo perdido: 2-3 horas por posición
Impacto: Alto - RRHH saturado
Workaround: Filtrar por palabras clave básicas
Prioridad: Alta

Q1: Criterios de selección
Contexto: Paso 4 (revisar CVs)
Pregunta: ¿Cuáles son los criterios específicos? ¿Hay scoring automático?
Respuesta esperada: Lista de criterios ponderados
Estado: Pendiente
```

---

## Técnicas de Registro

### Técnica 1: Registro en Tiempo Real

**Durante la sesión:**
1. Escucha activa mientras el usuario narra
2. Identifica variaciones/pain points/errores
3. Regístralas inmediatamente con formato estándar
4. Usa códigos simples (V1, E1, P1)
5. Marca el paso donde aparecen

**Ejemplo de registro en vivo:**
```
Usuario: "Y aquí siempre se atasca porque la impresora está rota..."
Tú: *anota* [P1] Impresora rota - Paso 3 - 90% frecuencia - 15min perdidos
Usuario: "A veces, si es cliente premium, saltamos esto..."
Tú: *anota* [V1] Cliente premium - Paso 4 - 20% -跳过 aprobación
```

### Técnica 2: Registro Diferido

**Después de la sesión:**
1. Revisa las notas tomadas
2. Clasifica cada anotación por tipo
3. Asigna códigos únicos
4. Completa detalles faltantes
5. Valida con el experto si es necesario

### Técnica 3: Agrupación Temática

**Para procesos complejos:**
1. Agrupa anotaciones por tema
2. Usa sub-códigos si necesario (V1a, V1b)
3. Mantén referencia a historia principal
4. Crea índice de anotaciones

**Ejemplo:**
```
V1: Cliente premium
  V1a: Skip aprobación (30%)
  V1b: Descuento automático (100%)
```

---

## Organización y Estructura

### Estructura Recomendada

```
ANOTACIONES - [Nombre de Historia]

=== VARIACIONES (V) ===
V1: [Título]
...

=== ERRORES/EXCEPCIONES (E) ===
E1: [Título]
...

=== ASUNCIONES (A) ===
A1: [Título]
...

=== PAIN POINTS (P) ===
P1: [Título]
...

=== PREGUNTAS (Q) ===
Q1: [Título]
...

=== INFORMACIÓN ADICIONAL (I) ===
I1: [Título]
...
```

### Priorización de Anotaciones

#### Criterios de Prioridad

**Alta Prioridad:**
- Frecuencia > 20%
- Impacto alto
- Bloquea implementación
- Afecta muchos usuarios

**Media Prioridad:**
- Frecuencia 5-20%
- Impacto medio
- Afecta eficiencia
- Workaround disponible

**Baja Prioridad:**
- Frecuencia < 5%
- Impacto bajo
- Nice to have
- Fácil de implementar

#### Matriz de Priorización

| Frecuencia | Impacto Alto | Impacto Medio | Impacto Bajo |
|------------|--------------|---------------|--------------|
| >20% | 🔴 CRÍTICA | 🟡 ALTA | 🟢 MEDIA |
| 5-20% | 🟡 ALTA | 🟢 MEDIA | 🔵 BAJA |
| <5% | 🟢 MEDIA | 🔵 BAJA | ⚪ BAJA |

---

## Uso de Anotaciones

### Durante Implementación

**Sprint 1:** Solo historia principal
- Implementar happy path completo
- Testing del flujo principal
- Validación con usuarios

**Sprint 2:** Variaciones críticas
- Implementar variaciones de alta prioridad
- Manejo de errores críticos
- Testing de variaciones

**Sprint 3:** Refinamiento
- Pain points de alta prioridad
- Automatización de procesos manuales
- Optimizaciones

**Sprint 4:** Completitud
- Variaciones restantes
- Documentación completa
- Testing exhaustivo

### Para Validación con Usuarios

**Sesión 1:** Validar historia principal
- "¿Esto refleja el proceso ideal?"
- "¿Falta algo en el happy path?"

**Sesión 2:** Revisar variaciones
- "Hablemos de estas variaciones..."
- "¿Qué tan frecuentes son?"

**Sesión 3:** Priorizar pain points
- "¿Cuáles son los problemas más urgentes?"
- "¿Qué impacto tienen?"

---

## Herramientas de Apoyo

### Template de Anotación Rápida

**Durante sesión (formato abreviado):**
```
[TIPO][ID]: [1-5 palabras]
Paso: [X] | Freq: [%]
Descripción: [1 línea]
Prioridad: [H/M/B]
```

**Ejemplos:**
```
V1: Premium skip aprobación
Paso: 4 | Freq: 20%
Descripción: Clientes premium no requieren aprobación
Prioridad: H

P1: Transcripción manual
Paso: 3 | Freq: 30%
Descripción: Errores al copiar datos entre sistemas
Prioridad: H
```

### Checklist de Registro

**Para cada anotación:**
- [ ] ¿Tiene tipo claro (V/E/A/P/Q/I)?
- [ ] ¿Tiene código único?
- [ ] ¿Indica contexto (paso)?
- [ ] ¿Tiene descripción clara?
- [ ] ¿Tiene prioridad asignada?
- [ ] ¿Es accionable?

### Palabras Clave para Identificar

**Variaciones:**
- "Si es..."
- "Cuando..."
- "A veces..."
- "Dependiendo de..."

**Pain Points:**
- "Siempre se atasca..."
- "Es muy tedioso..."
- "Perdemos tiempo..."
- "Aquí es problemático..."

**Errores:**
- "Si falla..."
- "Cuando no funciona..."
- "Si pasa X..."

**Asunciones:**
- "Normalmente..."
- "Asumimos que..."
- "Siempre..."

---

## Resumen: Sistema de Anotaciones

### Principios Fundamentales

1. **Separación clara** - Historia principal vs. anotaciones
2. **Referencias cruzadas** - Contexto de dónde aparecen
3. **Clasificación consistente** - Tipos y códigos estándar
4. **Formato estandarizado** - Fácil de leer y mantener
5. **Priorización** - Enfoque en lo importante primero

### Beneficios Clave

- ✅ **Historia principal limpia** y fácil de implementar
- ✅ **Variaciones organizadas** y clasificadas
- ✅ **Progressive disclosure** - complejidad gradual
- ✅ **Feedback temprano** - validar base primero
- ✅ **Flexible** - agregar complejidad cuando sea necesario

### Frases Clave

**Para registrar:**
- "Lo anoto como variación..."
- "Esto va en anotaciones..."
- "Como pain point, lo marcamos..."
- "Asunción importante..."

**Para clasificar:**
- "¿Es común o excepcional?"
- "¿Qué impacto tiene?"
- "¿Es un error o una variación?"
- "¿Cuánta frecuencia?"

**Recuerda:** Las anotaciones son tu herramienta para manejar complejidad sin perder simplicidad. La historia principal debe ser lo más simple posible, y todas las complejidades van en anotaciones organizadas y clasificadas.
