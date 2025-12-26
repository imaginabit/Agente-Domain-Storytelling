# Variaciones y Anotaciones

Este documento explica cómo identificar, registrar y organizar variaciones y excepciones sin complicar la historia principal del happy path, manteniendo la simplicidad mientras se captura la complejidad completa del dominio.

## ¿Por qué Separar Variaciones?

### Problemas con Mezclar Variaciones en Historia Principal

❌ **Complejidad excesiva** - La historia se vuelve inmanejable
❌ **Difícil de seguir** - El lector pierde el hilo principal
❌ **Complejo de modelar** - Software con muchas ramas
❌ **Estado inconsistente** - Múltiples paths posibles
❌ **Testing difícil** - Cada combinación requiere tests
❌ **Implementación lenta** - Todo debe hacerse junto

### Beneficios de Separar Variaciones

✅ **Historia principal clara** - Happy path sin complicaciones
✅ **Fácil de implementar** - Empezar por lo simple
✅ **Testing incremental** - Validar base antes de variaciones
✅ **Feedback temprano** - Usuarios validan flujo principal
✅ **Scope controlado** - Evitar scope creep
✅ **Evolución progresiva** - Agregar complejidad gradualmente

---

## Tipos de Variaciones

### 1. Variaciones de Flujo (Alternative Paths)

**Características:**
- Cambian la secuencia de pasos
- Toman ruta diferente en algún punto
- Pueden reconectarse con el flujo principal

**Ejemplos:**
- "Si es cliente premium, saltamos el paso de aprobación"
- "Cuando falla la validación, enviamos error"
- "Si es emergencia, priorizamos la orden"

### 2. Variaciones de Actor (Different Actors)

**Características:**
- Mismo proceso, actor diferente
- Cambia quién hace qué
- Flujo similar pero responsabilidades distintas

**Ejemplos:**
- "Si el cliente es nuevo, RRHH hace X; si es existente, comercial hace X"
- "En turno de noche, el supervisor de guardia hace Y"
- "Para clientes enterprise, el director hace Z"

### 3. Variaciones de Objeto (Different Objects)

**Características:**
- Mismo proceso, objeto diferente
- El "qué" cambia, el "cómo" es similar
- Tipos, categorías, estados distintos

**Ejemplos:**
- "Para órdenes de tipo A, proceso X; para tipo B, proceso Y"
- "Si el material es peligroso, protocolo especial"
- "Para empleados temporales, proceso simplificado"

### 4. Variaciones de Condición (Conditional Variations)

**Características:**
- Dependen de una condición específica
- Pueden o no ocurrir
- Basadas en reglas de negocio

**Ejemplos:**
- "Si el importe > 1000€, requiere aprobación"
- "Si el cliente no responde en 48h, enviar recordatorio"
- "Si hay stock suficiente, enviar inmediatamente"

### 5. Variaciones de Error (Error Paths)

**Características:**
- Ocurren cuando algo falla
- Manejo de excepciones
- Recuperación de errores

**Ejemplos:**
- "Si el sistema falla, usar proceso manual"
- "Si no hay técnico disponible, reprogramar"
- "Si el cliente rechaza, ofrecer alternativa"

### 6. Variaciones de Tiempo (Temporal Variations)

**Características:**
- Dependen del momento/tiempo
- Calendario, horarios, plazos
- Eventos temporales

**Ejemplos:**
- "En fin de semana, solo urgencias"
- "Si pasa un mes, caduca la solicitud"
- "Durante horario nocturno, proceso diferente"

---

## Identificación de Variaciones

### Señales en la Narrativa Original

| Tipo de Frase | Ejemplo | Tipo de Variación |
|---------------|---------|-------------------|
| **Condicionales** | "Si..., entonces..." | Condicional |
| **Frecuencia** | "A veces...", "Ocasionalmente..." | Frecuencia |
| **Alternativas** | "Dependiendo de..." | Actor/Objeto |
| **Excepciones** | "Excepto cuando..." | Condicional |
| **Tiempo** | "Después de X tiempo..." | Temporal |
| **Errores** | "Si falla..." | Error |
| **Comparación** | "Para X..., para Y..." | Actor/Objeto |

### Preguntas para Identificar Variaciones

**Para detectar condicionales:**
- "¿Eso es común o excepcional?"
- "¿Qué porcentaje de casos?"
- "¿Es el 80% o el 20%?"
- "¿Es el caso normal o especial?"

**Para detectar alternativas:**
- "¿Qué otros tipos existen?"
- "¿Cuándo se usa cada uno?"
- "¿Cuáles son las diferencias?"
- "¿Cuál es más común?"

**Para detectar errores:**
- "¿Eso pasa cuando todo va bien o mal?"
- "¿Es el camino feliz o de error?"
- "¿Con qué frecuencia ocurre?"
- "¿Cómo se recupera?"

---

## Técnicas de Registro

### Técnica 1: Lista de Anotaciones en Tiempo Real

**Proceso:**
1. **Escucha activa** mientras el usuario narra
2. **Identifica variaciones** cuando aparecen
3. **Regístralas aparte** sin interrumpir el flujo
4. **Anota el contexto** donde aparecen
5. **Retoma el happy path** inmediatamente

**Ejemplo:**

**Usuario:** "Entonces RRHH verifica documentos. Si están completos, crea expediente. Si falta algo, lo pide. Después genera contrato..."

**Tú:**
```
[ANOTACIÓN 1] Variación: Documentación incompleta
  Contexto: Paso 2 (verificación de documentos)
  Acción: RRHH solicita documentos faltantes

[ANOTACIÓN 2] Continuar con happy path: RRHH genera contrato
```

**Plantilla de Anotación:**
```
[ANOTACIÓN N] [Nombre descriptivo]
  Contexto: [Paso donde aparece]
  Condición: [Cuándo ocurre]
  Acción: [Qué pasa]
  Frecuencia: [¿Común o excepcional?]
```

### Técnica 2: Códigos de Identificación

**Sistema de códigos:**
- **V#:** Variación de flujo
- **A#:** Variación de actor
- **O#:** Variación de objeto
- **C#:** Variación condicional
- **E#:** Variación de error
- **T#:** Variación temporal

**Ejemplo:**
```
V1: Cliente premium (salta aprobación)
A1: Turno noche (actor diferente)
E1: Sistema caído (manejo de error)
T1: Fin de semana (tiempo específico)
```

### Técnica 3: Historias Paralelas Numeradas

**Proceso:**
1. **Historia principal:** 1, 2, 3, 4, 5...
2. **Variación A:** A1, A2, A3...
3. **Variación B:** B1, B2, B3...
4. **Cada variación** independiente pero relacionada

**Ejemplo:**
```
Historia Principal (Cliente estándar):
1. `Cliente solicita servicio`
2. `Comercial evalúa solicitud`
3. `Comercial aprueba solicitud`
4. `Operaciones ejecuta servicio`
5. `Cliente recibe servicio`

Variación A (Cliente premium):
A1. `Cliente premium solicita servicio`
A2. `Sistema marca como premium`
A3. `Comercial aprueba automáticamente`
A4. `Operaciones ejecuta servicio` (reconexión)

Variación B (Solicitud rechazada):
B1. `Cliente solicita servicio`
B2. `Comercial evalúa solicitud`
B3. `Comercial rechaza solicitud`
B4. `Cliente recibe notificación de rechazo`
```

---

## Organización de Variaciones

### Nivel 1: Clasificación por Frecuencia

#### Variaciones Comunes (20-50% casos)
- **Tratamiento:** Historias prioritarias
- **Implementación:** Después del happy path
- **Testing:** Segunda prioridad

**Ejemplo:**
- "Si es cliente nuevo (30% casos)" → Historia B

#### Variaciones Poco Comunes (5-20% casos)
- **Tratamiento:** Historias secundarias
- **Implementación:** Iteración posterior
- **Testing:** Tercera prioridad

**Ejemplo:**
- "Si hay emergencia (10% casos)" → Historia C

#### Variaciones Raras (<5% casos)
- **Tratamiento:** Historias de baja prioridad
- **Implementación:** Solo si hay tiempo
- **Testing:** Opcional

**Ejemplo:**
- "Si el sistema falla (2% casos)" → Historia D

### Nivel 2: Clasificación por Complejidad

#### Variaciones Simples (Un paso diferente)
**Implementación:** Fácil
**Ejemplo:** "Si es cliente premium, saltar aprobación"

#### Variaciones Medias (Múltiples pasos diferentes)
**Implementación:** Moderada
**Ejemplo:** "Si es cliente nuevo, proceso completo de verificación"

#### Variaciones Complejas (Proceso completamente diferente)
**Implementación:** Difícil
**Ejemplo:** "Si es emergencia, protocolo especial completo"

### Nivel 3: Clasificación por Impacto

#### Alto Impacto (Afectan negocio)
- Historias críticas
- Prioridad alta

#### Medio Impacto (Afectan experiencia)
- Historias importantes
- Prioridad media

#### Bajo Impacto (Nice to have)
- Historias deseables
- Prioridad baja

---

## Templates para Documentar Variaciones

### Template Completo

```
VARIACIÓN #[ID]: [Nombre descriptivo]

CONTEXTO:
- Historia principal: [Número de historia]
- Paso donde diverge: [Paso X]
- Porcentaje de casos: [%]

CONDICIÓN:
- Trigger: [¿Qué la activa?]
- Criterio: [¿Cómo se detecta?]
- Frecuencia: [¿Con qué frecuencia?]

FLUJO ALTERADO:
1. [Paso específico de variación]
2. [Otro paso...]
3. [Reconexión o final]

RECONEXIÓN:
- ¿Se reconecta con principal? [Sí/No]
- En qué paso: [Paso X]

PRIORIDAD:
- Implementación: [Alta/Media/Baja]
- Testing: [Alta/Media/Baja]
- Complejidad: [Alta/Media/Baja]

NOTAS:
- [Observaciones adicionales]
- [Dependencias]
- [Consideraciones especiales]
```

### Template Simplificado

```
VARIACIÓN [ID]: [Nombre]
Frecuencia: [%]
Diverge en: Paso [X]
Cambios:
- [Lista de pasos alterados]
Reconexión: Paso [Y] / No reconecta
Prioridad: [H/M/B]
```

---

## Ejemplos Completos de Variaciones

### Ejemplo 1: Proceso de Contratación

#### Historia Principal (Happy Path)
```
1. `RRHH recibe solicitud de personal`
2. `RRHH publica oferta de empleo`
3. `Candidatos envían currículums`
4. `Recruiter revisa CVs`
5. `Recruiter selecciona candidatos`
6. `RRHH programa entrevistas`
7. `Candidatos asisten a entrevistas`
8. `RRHH selecciona candidato final`
9. `RRHH prepara contrato`
10. `Candidato firma contrato`
11. `RRHH registra empleado`
```

#### Variación A: Contratación Urgente (20% casos)
```
VARIACIÓN A: Contratación urgente
Frecuencia: 20%
Diverge en: Paso 2 (publicar oferta)

A1. `RRHH recibe solicitud urgente`
A2. `RRHH identifica como urgente`
A3. `RRHH publica en portales de alta rotación`
A4. `RRHH contacta headhunters`
A5. `Proceso continúa desde paso 3`

Reconexión: Paso 3 (candidatos envían CVs)
Prioridad: Alta
```

#### Variación B: Candidatos Externos (10% casos)
```
VARIACIÓN B: Presentados por headhunter
Frecuencia: 10%
Diverge en: Paso 3 (candidatos envían CVs)

B1. `Headhunter presenta candidatos`
B2. `RRHH recibe candidatos de headhunter`
B3. `Proceso continúa desde paso 4 (revisar CVs)`

Reconexión: Paso 4 (revisar CVs)
Prioridad: Media
```

#### Variación C: No hay Candidatos Válidos (5% casos)
```
VARIACIÓN C: Rechazo masivo
Frecuencia: 5%
Diverge en: Paso 5 (seleccionar candidatos)

C1. `Recruiter revisa CVs`
C2. `Recruiter evalúa candidatos`
C3. `NINGÚN candidato cumple criterios`
C4. `RRHH decide reposticionar oferta`
C5. `Vuelve al paso 2 (republicar)`

Reconexión: Paso 2 (publicar oferta)
Prioridad: Media
```

#### Variación D: Candidato Rechaza Oferta (15% casos)
```
VARIACIÓN D: Candidato declina
Frecuencia: 15%
Diverge en: Paso 9 (seleccionar candidato final)

D1. `RRHH prepara contrato`
D2. `Candidato revisa contrato`
D3. `Candidato rechaza oferta`
D4. `RRHH ofrece al segundo candidato`
D5. `Vuelve al paso 9 (con segundo candidato)`

Reconexión: Paso 9 (con siguiente candidato)
Prioridad: Alta
```

### Ejemplo 2: Proceso de Facturación

#### Historia Principal (Happy Path)
```
1. `Orden de trabajo se completa`
2. `Técnico genera parte de trabajo`
3. `Sistema calcula costes automáticamente`
4. `Administrativo crea factura`
5. `Administrativo envía factura al cliente`
6. `Cliente recibe factura`
7. `Cliente paga factura`
```

#### Variación A: Factura > 1000€ (30% casos)
```
VARIACIÓN A: Aprobación requerida
Frecuencia: 30%
Diverge en: Paso 4 (crear factura)

A1. `Administrativo revisa importe`
A2. `Importe > 1000€`
A3. `Sistema solicita aprobación director`
A4. `Director aprueba factura`
A5. `Proceso continúa desde paso 4 (crear factura)`

Reconexión: Paso 4 (crear factura)
Prioridad: Alta
```

#### Variación B: Cliente Nuevo (15% casos)
```
VARIACIÓN B: Cliente nuevo
Frecuencia: 15%
Diverge en: Paso 4 (crear factura)

B1. `Administrativo identifica cliente nuevo`
B2. `Administrativo solicita datos fiscales`
B3. `Cliente proporciona datos`
B4. `Administrativo valida datos`
B5. `Proceso continúa desde paso 4 (crear factura)`

Reconexión: Paso 4 (crear factura)
Prioridad: Media
```

#### Variación C: Cliente No Responde (25% casos)
```
VARIACIÓN C: No respuesta
Frecuencia: 25%
Diverge en: Paso 6 (cliente recibe factura)

C1. `Cliente recibe factura`
C2. `Cliente NO responde`
C3. `Sistema espera 15 días`
C4. `Sistema envía recordatorio`
C5. `Cliente recibe recordatorio`
C6. `Cliente paga factura` / `Cliente sigue sin responder`

Reconexión: Paso 7 (pago) o final alternativo
Prioridad: Media
```

### Ejemplo 3: Proceso de Control de Calidad

#### Historia Principal (Happy Path)
```
1. `Producto llega a control de calidad`
2. `Inspector recibe producto`
3. `Inspector realiza pruebas`
4. `Producto cumple estándares`
5. `Inspector etiqueta APROBADO`
6. `Inspector registra resultado`
7. `Producto va a almacén`
```

#### Variación A: Producto No Conforme (8% casos)
```
VARIACIÓN A: Rechazo
Frecuencia: 8%
Diverge en: Paso 4 (cumple estándares)

A1. `Inspector realiza pruebas`
A2. `Producto NO cumple estándares`
A3. `Inspector etiqueta RECHAZADO`
A4. `Producto va a área de reproceso`
A5. `Inspector registra no conformidad`

Final alternativo: No reconecta
Prioridad: Alta
```

#### Variación B: Producto Especial (3% casos)
```
VARIACIÓN B: Requiere revisión especial
Frecuencia: 3%
Diverge en: Paso 3 (realizar pruebas)

B1. `Inspector identifica producto especial`
B2. `Inspector llama a responsable de calidad`
B3. `Responsable de calidad realiza pruebas adicionales`
B4. `Responsable de calidad decide aprobación`
B5. `Proceso continúa desde paso 4 (cumplir estándares)`

Reconexión: Paso 4 (cumplir estándares)
Prioridad: Media
```

#### Variación C: Muestra Defectuosa (2% casos)
```
VARIACIÓN C: Muestra defectuosa
Frecuencia: 2%
Diverge en: Paso 2 (recibir producto)

C1. `Inspector recibe producto`
C2. `Inspector detecta muestra defectuosa`
C3. `Inspector rechaza la muestra`
C4. `Se solicita nueva muestra`
C5. `Proceso reinicia desde paso 1`

Reconexión: Paso 1 (nueva muestra)
Prioridad: Baja
```

---

## Priorización para Implementación

### Matriz de Priorización

| Frecuencia | Complejidad | Impacto | Prioridad Final |
|------------|------------|---------|-----------------|
| Alta (>20%) | Baja | Alto | 🔴 CRÍTICA |
| Alta (>20%) | Media | Alto | 🔴 CRÍTICA |
| Alta (>20%) | Alta | Alto | 🟡 ALTA |
| Media (5-20%) | Baja | Alto | 🟡 ALTA |
| Media (5-20%) | Media | Medio | 🟢 MEDIA |
| Baja (<5%) | Baja | Medio | 🟢 MEDIA |
| Baja (<5%) | Alta | Bajo | ⚪ BAJA |

### Roadmap Sugerido

#### Sprint 1 (Base)
- ✅ Implementar Happy Path completo
- ✅ Testing del flujo principal
- ✅ Validación con usuarios

#### Sprint 2 (Variaciones Críticas)
- 🔴 Implementar variaciones críticas (alta freq + alto impacto)
- 🔴 Testing de variaciones críticas
- 🔴 Integración con happy path

#### Sprint 3 (Variaciones Importantes)
- 🟡 Implementar variaciones importantes (media freq/impacto)
- 🟡 Testing de variaciones importantes
- 🟡 Refinamiento

#### Sprint 4 (Variaciones Adicionales)
- 🟢 Implementar variaciones restantes
- 🟢 Testing completo
- 🟢 Documentación final

---

## Resumen: Manejo de Variaciones

### Principios Fundamentales

1. **Happy Path primero** - Siempre documentar el camino principal
2. **Variaciones aparte** - Nunca en la historia principal
3. **Clasificar por frecuencia** - 80/20 rule
4. **Organizar sistemáticamente** - Templates y códigos
5. **Priorizar implementación** - Roadmap incremental
6. **Validar cada variación** - Testing independiente

### Frases Clave para el Usuario

**Para redirigir al happy path:**
- "Anoto eso para después..."
- "Sigamos con el caso normal..."
- "Hablemos del 80% primero..."
- "Eso va en una variación..."

**Para clasificar variaciones:**
- "¿Qué porcentaje de casos?"
- "¿Es común o excepcional?"
- "¿Cuándo ocurre?"
- "¿Con qué frecuencia?"

**Para organizar:**
- "¿Es una variación de flujo, actor o condición?"
- "¿Se reconecta o es final alternativo?"
- "¿Alta, media o baja prioridad?"

**Recuerda:** La clave está en la disciplina. Resistir la tentación de documentar todo de una vez y enfocarse en el camino principal primero. Las variaciones pueden esperar, pero el happy path es la base sobre la cual construir.
