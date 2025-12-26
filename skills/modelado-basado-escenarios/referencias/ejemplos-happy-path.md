# Ejemplos de Happy Path (Camino Principal)

Este documento contiene ejemplos reales de captura del camino principal en procesos empresariales, mostrando cómo identificar y documentar el 80% de casos sin excepciones.

## Principios del Happy Path

### ¿Qué es el Happy Path?
El **Happy Path** es el flujo ideal que ocurre en el 80% de los casos sin excepciones, variaciones o complicaciones. Es el camino "normal" que los expertos del dominio esperan que ocurra la mayoría de las veces.

### Características del Happy Path:
- ✅ **Flujo lineal** sin ramificaciones
- ✅ **Sin condicionales** (if/else, casos especiales)
- ✅ **Sin excepciones** (error handling, fallos)
- ✅ **Sin variaciones** (múltiples formas de hacer algo)
- ✅ **Sin mejoras** (solo proceso actual o futuro ideal)

### ¿Por qué empezar por el Happy Path?
1. **Es más fácil** de capturar y entender
2. **Es más simple** de modelar y documentar
3. **Establece la base** sobre la cual construir
4. **Reduce complejidad** inicial
5. **Crea consenso** más rápido entre stakeholders

---

## Ejemplo 1: Proceso de Alta de Empleado (RRHH)

### Narrativa Original (con variaciones)
"El nuevo empleado viene con su documentación. RRHH verifica los documentos. Si están todos, creamos el expediente. Si falta algo, pedimos que lo traiga. Después generamos el contrato. Luego el empleado lo firma. A veces el contrato se envía por email, otras veces lo firma presencialmente. Después de firmar, RRHH registra al empleado en el sistema de nóminas..."

### Análisis del Happy Path
**Frase clave:** "Si están todos..." → Detecta condicional
**Variaciones detectadas:**
- "Si falta algo..." → Variación
- "A veces... otras veces..." → Variación

### Happy Path Capturado
**Pregunta inicial:** "¿En el caso normal, cuando un empleado trae toda la documentación, qué pasa?"

**Respuesta:** "Entonces RRHH verifica los documentos, crea el expediente, genera el contrato, el empleado lo firma presencialmente y RRHH lo registra en nóminas."

### Historia Estructurada (Happy Path)
1. `El nuevo empleado trae toda la documentación`
2. `RRHH recibe la documentación completa`
3. `RRHH verifica que todos los documentos están correctos`
4. `RRHH crea el expediente del empleado`
5. `RRHH genera el contrato laboral`
6. `El empleado firma el contrato presencialmente`
7. `RRHH registra al empleado en el sistema de nóminas`
8. `El sistema asigna automáticamente número de empleado`

### Variaciones (Historias Separadas)
**Anotación 1:** `Variación A: Documentación incompleta`
- Paso 3 alternativo: `RRHH identifica documentos faltantes`
- Paso 4 alternativo: `RRHH solicita documentos faltantes al empleado`
- Regresa al paso 3 hasta completar

**Anotación 2:** `Variación B: Contrato por email`
- Paso 6 alternativo: `RRHH envía contrato por email al empleado`
- Paso 6.1: `El empleado firma el contrato digitalmente`

---

## Ejemplo 2: Proceso de Facturación (Finanzas)

### Narrativa Original (con variaciones)
"Cuando se completa una orden de trabajo, el técnico genera el parte de trabajo. Luego el sistema calcula automáticamente los costes. Si es cliente nuevo, necesitamos datos adicionales. El departamento administrativo crea la factura. Si el importe es mayor a 1000€, requiere aprobación del director. Si el cliente aprueba, enviamos la factura. Si no responde en 30 días, enviamos recordatorio..."

### Análisis del Happy Path
**Condicionales detectados:**
- "Si es cliente nuevo..." → Variación
- "Si el importe es mayor a 1000€..." → Variación
- "Si el cliente aprueba..." → Variación
- "Si no responde en 30 días..." → Variación

### Happy Path Capturado
**Pregunta:** "Hablemos del caso más común: cliente existente, factura menor a 1000€. ¿Qué ocurre?"

**Respuesta:** "El técnico genera el parte, el sistema calcula costes, administrativo crea la factura y se envía al cliente."

### Historia Estructurada (Happy Path)
1. `El técnico completa la orden de trabajo`
2. `El técnico genera el parte de trabajo`
3. `El sistema calcula automáticamente los costes`
4. `El departamento administrativo crea la factura`
5. `El departamento administrativo envía la factura al cliente`
6. `El cliente recibe la factura`

### Variaciones (Historias Separadas)
**Anotación 1:** `Variación A: Cliente nuevo`
- Paso 4 alternativo: `El departamento administrativo solicita datos adicionales al cliente`
- Paso 4.1: `El cliente proporciona los datos solicitados`
- Continúa al paso 4 (crear factura)

**Anotación 2:** `Variación B: Factura > 1000€`
- Paso 5 alternativo: `El director aprueba la factura`
- Continúa al paso 5 (enviar factura)

**Anotación 3:** `Variación C: No respuesta del cliente`
- Paso 6.1: `El sistema espera 30 días`
- Paso 6.2: `El sistema envía recordatorio de pago`

---

## Ejemplo 3: Proceso de Solicitud de Vacaciones (RRHH)

### Narrativa Original (con variaciones)
"El empleado solicita vacaciones en el sistema. El sistema valida días disponibles. Si tiene días suficientes, envía la solicitud al supervisor. El supervisor revisa considerando la carga de trabajo. Si está todo bien, aprueba. Si hay conflicto, propone fechas alternativas. El empleado recibe la aprobación..."

### Análisis del Happy Path
**Condicionales detectados:**
- "Si tiene días suficientes..." → Variación
- "Si está todo bien..." → Variación
- "Si hay conflicto..." → Variación
- "Si está todo bien..." → Variación

### Happy Path Capturado
**Pregunta:** "¿Cuál es el caso más común? ¿El empleado siempre tiene días disponibles?"

**Respuesta:** "Sí, normalmente tiene días suficientes y no hay conflictos."

### Historia Estructurada (Happy Path)
1. `El empleado accede al sistema de RRHH`
2. `El empleado solicita vacaciones indicando fechas`
3. `El sistema valida que tiene días disponibles`
4. `El sistema envía la solicitud al supervisor`
5. `El supervisor revisa la solicitud`
6. `El supervisor aprueba la solicitud`
7. `El sistema actualiza el calendario de vacaciones`
8. `El empleado recibe notificación de aprobación`

### Variaciones (Historias Separadas)
**Anotación 1:** `Variación A: Días insuficientes`
- Paso 3 alternativo: `El sistema rechaza la solicitud por días insuficientes`

**Anotación 2:** `Variación B: Conflicto de fechas`
- Paso 6 alternativo: `El supervisor propone fechas alternativas`
- Paso 6.1: `El empleado acepta las fechas propuestas o propone otras`
- Vuelve al paso 6 (aprobar o proponer)

---

## Ejemplo 4: Proceso de Creación de Orden de Trabajo (Operaciones)

### Narrativa Original (con variaciones)
"El cliente solicita un servicio. El departamento comercial crea una orden preliminar. El responsable de operaciones revisa la orden. Si hay técnicos disponibles, asigna uno. Si no, programa para más adelante. El técnico recibe la orden. Si es emergencia, se prioriza. Si no, sigue su agenda..."

### Análisis del Happy Path
**Condicionales detectados:**
- "Si hay técnicos disponibles..." → Variación
- "Si no..." → Variación (continuación)
- "Si es emergencia..." → Variación
- "Si no..." → Variación (continuación)

### Happy Path Capturado
**Pregunta:** "En el caso normal, ¿siempre hay técnicos disponibles?"

**Respuesta:** "Sí, normalmente asignamos inmediatamente sin problemas."

### Historia Estructurada (Happy Path)
1. `El cliente solicita un servicio`
2. `El departamento comercial crea la orden preliminar`
3. `El responsable de operaciones revisa la orden`
4. `El responsable de operaciones asigna un técnico disponible`
5. `El técnico recibe la orden en su sistema`
6. `El técnico se desplaza al lugar del servicio`
7. `El técnico realiza el servicio`
8. `El técnico completa el parte de trabajo`

### Variaciones (Historias Separadas)
**Anotación 1:** `Variación A: No hay técnicos disponibles`
- Paso 4 alternativo: `El responsable de operaciones programa la orden para una fecha posterior`
- Continúa cuando hay disponibilidad

**Anotación 2:** `Variación B: Emergencia`
- Paso 6 alternativo: `El técnico prioriza la orden de emergencia`

---

## Ejemplo 5: Proceso de Control de Calidad (Calidad)

### Narrativa Original (con variaciones)
"Cada producto pasa por control de calidad. El inspector realiza pruebas. Si cumple estándares, se aprueba. Si no, se rechaza y va a reproceso. Los productos aprobados se envían al cliente. Los rechazados se reparan. A veces hay productos que requieren revisión especial..."

### Análisis del Happy Path
**Condicionales detectados:**
- "Si cumple estándares..." → Variación
- "Si no..." → Variación (continuación)
- "A veces..." → Variación

### Happy Path Capturado
**Pregunta:** "¿Cuál es el caso más normal? ¿Los productos normalmente cumplen estándares?"

**Respuesta:** "Sí, el 90% de productos pasan sin problemas."

### Historia Estructurada (Happy Path)
1. `El producto llega al control de calidad`
2. `El inspector realiza pruebas según protocolo`
3. `El inspector verifica que cumple estándares`
4. `El producto cumple estándares`
5. `El inspector etiqueta el producto como APROBADO`
6. `El producto se envía al cliente`

### Variaciones (Historias Separadas)
**Anotación 1:** `Variación A: Producto no conforme`
- Paso 4 alternativo: `El producto NO cumple estándares`
- Paso 5 alternativo: `El inspector etiqueta el producto como RECHAZADO`
- Paso 6 alternativo: `El producto va a reproceso`

**Anotación 2:** `Variación B: Revisión especial`
- Paso 3 alternativo: `El producto requiere revisión especial del responsable`

---

## Ejemplo 6: Proceso de Compra de Materiales (Compras)

### Narrativa Original (con variaciones)
"El departamento de producción solicita materiales. El buyer analiza la solicitud. Busca proveedores en el catálogo. Si encuentra el material, solicita cotización. Si no, busca proveedores alternativos. El proveedor envía cotización. Si el precio es competitivo, se acepta. Si no, se negocia..."

### Análisis del Happy Path
**Condicionales detectados:**
- "Si encuentra el material..." → Variación
- "Si no..." → Variación (continuación)
- "Si el precio es competitivo..." → Variación
- "Si no..." → Variación (continuación)

### Happy Path Capturado
**Pregunta:** "¿En el caso normal, siempre encuentran el material en el catálogo y el precio es correcto?"

**Respuesta:** "Sí, normalmente el proveedor principal tiene disponibilidad y precios acordes."

### Historia Estructurada (Happy Path)
1. `El departamento de producción solicita materiales`
2. `El buyer analiza la solicitud`
3. `El buyer busca proveedores en el catálogo`
4. `El buyer encuentra el material disponible`
5. `El buyer solicita cotización al proveedor`
6. `El proveedor envía la cotización`
7. `El buyer evalúa la cotización`
8. `El buyer acepta la cotización`
9. `El responsable de compras aprueba la orden`
10. `El sistema envía la orden al proveedor`

### Variaciones (Historias Separadas)
**Anotación 1:** `Variación A: Material no disponible en catálogo`
- Paso 4 alternativo: `El buyer NO encuentra el material en el catálogo`
- Paso 4.1: `El buyer busca proveedores alternativos`
- Continúa al paso 5

**Anotación 2:** `Variación B: Precio no competitivo`
- Paso 8 alternativo: `El buyer negocia el precio con el proveedor`
- Paso 8.1: `El proveedor acepta negociar`
- Vuelve al paso 8 (aceptar)

---

## Guía para Identificar el Happy Path

### Señales en la Narrativa Original

| Indicador | Ejemplo | Acción |
|-----------|---------|--------|
| **"Si..."** | "Si pasa X, entonces Y" | Detener y redirigir al caso normal |
| **"A veces..."** | "A veces hacemos X, otras Y" | Capturar primero el "a veces" más común |
| **"Normalmente..."** | "Normalmente pasa X" | ¡Esto ES el happy path! |
| **"Generalmente..."** | "Generalmente ocurre Y" | ¡Esto ES el happy path! |
| **"Típicamente..."** | "Típicamente hacemos Z" | ¡Esto ES el happy path! |
| **"Excepto cuando..."** | "Siempre X, excepto cuando Y" | Capturar "siempre X" como happy path |
| **"A menos que..."** | "Hacemos X a menos que Y" | Capturar "hacemos X" como happy path |

### Preguntas para Identificar Happy Path

1. **¿Qué ocurre la mayoría de las veces?**
   - ¿En el 80% de casos?
   - ¿Sin complicaciones?

2. **¿Cuál es el caso ideal?**
   - ¿El que todos esperan?
   - ¿El más eficiente?

3. **¿Qué pasa cuando todo va bien?**
   - ¿Sin errores?
   - ¿Sin excepciones?

4. **¿Cuál es el flujo más simple?**
   - ¿El que tiene menos pasos?
   - ¿El más directo?

### Redirecciones Útiles

**Cuando el usuario menciona variaciones:**
- "Hablemos primero del caso más común"
- "¿Qué pasa normalmente?"
- "¿En el caso ideal?"
- "Concentrémonos en el 80% de casos"
- "¿Cómo ocurre la mayoría de las veces?"

**Para validar el happy path:**
- "¿Esto refleja el 80% de casos?"
- "¿Es el proceso ideal?"
- "¿Sin complicaciones?"
- "¿Es el flujo más simple?"

---

## Beneficios de Empezar por Happy Path

### Para el Usuario/Experto
- ✅ **Más fácil de explicar** (flujo natural vs. excepciones)
- ✅ **Menos abrumador** (sin complejidad inicial)
- ✅ **Más rápido de capturar** (memoria del caso típico)
- ✅ **Genera consenso** más fácil
- ✅ **Construye confianza** en el proceso

### Para el Modelador/Desarrollador
- ✅ **Base sólida** para construir
- ✅ **Menos refactoring** posterior
- ✅ **Lógica clara** sin ramas complejas
- ✅ **Fácil de implementar** primero
- ✅ **MVP más simple** para desarrollar

### Para el Proyecto
- ✅ **Entregas más rápidas** (happy path primero)
- ✅ **Menos riesgo** (funcionalidad core)
- ✅ **Feedback temprano** (validación con usuarios)
- ✅ **Evolución incremental** (variaciones después)
- ✅ **Scope más claro** (funcionalidad esencial)

---

## Resumen: Happy Path vs. Variaciones

| Aspecto | Happy Path (Principal) | Variaciones (Separadas) |
|---------|----------------------|-------------------------|
| **Porcentaje** | 80% de casos | 20% de casos |
| **Complejidad** | Baja | Media/Alta |
| **Narrativa** | Lineal | Ramificada |
| **Condicionales** | Ninguno | Múltiples |
| **Documentación** | Primero | Después |
| **Implementación** | MVP | Iteraciones |
| **Validación** | Inmediata | Diferida |
| **Beneficios** | Base sólida | Cobertura completa |

**Regla de oro:** Siempre documentar el Happy Path primero, las variaciones después. Una historia = un camino.
