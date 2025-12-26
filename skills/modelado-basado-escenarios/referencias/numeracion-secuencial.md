# Numeración Secuencial

Este documento explica cómo asignar y mantener un orden cronológico estricto en las historias de Domain Storytelling, asegurando que cada paso tenga su lugar temporal correcto.

## ¿Por qué la Numeración Secuencial?

### Importancia del Orden Cronológico
La numeración secuencial es crucial porque:

- ✅ **Establece causalidad clara** - Cada paso causa el siguiente
- ✅ **Facilita comprensión** - El lector sigue el flujo temporal
- ✅ **Ayuda en implementación** - El orden guía el desarrollo
- ✅ **Permite validación** - Fácil verificar completitud
- ✅ **Soporta testing** - Cada paso puede probarse secuencialmente

### Problemas sin Numeración
❌ **Ambigüedad temporal** - ¿Qué va antes, qué después?
❌ **Causalidad confusa** - ¿Qué causa qué?
❌ **Difícil de seguir** - El lector se pierde
❌ **Implementación errónea** - Orden incorrecto de desarrollo
❌ **Testing incompleto** - No se validan secuencias

---

## Principios de Numeración Secuencial

### Reglas Fundamentales

#### 1. Consecutividad
**Cada paso tiene un número único y consecutivo**

```
✅ Correcto:
1. El usuario hace X
2. El sistema hace Y
3. El usuario recibe Z

❌ Incorrecto:
1. El usuario hace X
3. El sistema hace Y (falta el 2!)
5. El usuario recibe Z (faltan 3 y 4!)
```

#### 2. Orden Temporal Estricto
**El número refleja cuándo ocurre, no qué importancia tiene**

```
✅ Correcto:
1. El empleado llega al trabajo (8:00 AM)
2. El empleado se registra en el sistema (8:01 AM)
3. El empleado empieza a trabajar (8:02 AM)
4. El empleado toma descanso (10:00 AM)
5. El empleado termina de trabajar (5:00 PM)

❌ Incorrecto (importancia vs tiempo):
1. El empleado llega al trabajo
2. El empleado termina de trabajar
3. El empleado se registra en el sistema
```

#### 3. Un Paso = Una Acción
**Cada número representa una sola acción**

```
✅ Correcto:
1. `El empleado completa el formulario`
2. `El empleado envía el formulario`
3. `El sistema recibe el formulario`

❌ Incorrecto (múltiples acciones):
1. `El empleado completa y envía el formulario` (dos acciones!)
```

#### 4. Un Actor por Paso
**Cada número tiene un actor principal**

```
✅ Correcto:
1. `El empleado → completa → formulario`
2. `Sistema → valida → datos`
3. `Empleado → recibe → confirmación`

❌ Incorrecto (múltiples actores):
1. `El empleado completa el formulario y el sistema valida` (dos actores!)
```

#### 5. Progresión Lógica
**Cada paso debe llevar naturalmente al siguiente**

```
✅ Correcto:
1. `El cliente solicita presupuesto`
2. `El vendedor recibe solicitud`
3. `El vendedor prepara presupuesto`
4. `El cliente recibe presupuesto`

❌ Incorrecto (salto lógico):
1. `El cliente solicita presupuesto`
2. `El cliente recibe factura` (¡saltó el medio!)
```

---

## Técnicas de Numeración

### Técnica 1: Escucha y Enumeración en Vivo

**Proceso:**
1. **Escucha activamente** la narrativa del usuario
2. **Identifica cada acción** mencionada
3. **Asigna número inmediatamente**
4. **Verifica secuencia** constantemente

**Ejemplo en acción:**

**Usuario:** "Cuando llega un cliente nuevo, primero se identifica, luego le preguntamos qué necesita, después evaluamos si podemos ayudarle, entonces preparamos una propuesta y finalmente la presentamos."

**Tú (numerando en tiempo real):**
1. `Llega un cliente nuevo`
2. `El cliente se identifica`
3. `El recepcionista pregunta qué necesita`
4. `El recepcionista evalúa si podemos ayudar`
5. `El vendedor prepara propuesta`
6. `El vendedor presenta la propuesta al cliente`

**Validación:** "¿El orden es correcto? ¿El recepcionista evalúa antes o después de preguntar qué necesita?"

---

### Técnica 2: Numeración por Disparadores de Eventos

**Proceso:**
1. **Identifica eventos** que inician procesos
2. **Numera desde el inicio** hasta el final
3. **Cada evento = un número**
4. **Mantiene orden de ocurrencia**

**Ejemplo:**
```
Evento disparador: "Cliente llama"

1. `El cliente llama al servicio de atención`
2. `El agente recibe la llamada`
3. `El agente saluda al cliente`
4. `El cliente explica su consulta`
5. `El agente clasifica la consulta`
6. `El agente resuelve la consulta`
7. `El agente confirma resolución`
8. `El agente cierra la llamada`
```

**Validación:** "¿El agente puede clasificar la consulta antes de que el cliente la explique?"

---

### Técnica 3: Numeración por Transiciones de Estado

**Proceso:**
1. **Identifica estado inicial**
2. **Numera cada transición**
3. **Finaliza en estado final**
4. **Cada transición = un número**

**Ejemplo - Solicitud de vacaciones:**
```
Estado inicial: SIN SOLICITAR

1. `El empleado solicita vacaciones` (SIN SOLICITAR → PENDIENTE)
2. `El sistema envía solicitud al supervisor` (PENDIENTE → EN REVISIÓN)
3. `El supervisor revisa la solicitud` (EN REVISIÓN → EVALUADA)
4. `El supervisor aprueba la solicitud` (EVALUADA → APROBADA)
5. `El sistema actualiza el calendario` (APROBADA → CONFIRMADA)
```

**Validación:** "¿Puede el supervisor revisar antes de recibir la solicitud?"

---

### Técnica 4: Numeración por Responsabilidades

**Proceso:**
1. **Identifica actor responsable**
2. **Ordena por responsabilidad**
3. **Mantiene secuencia lógica**
4. **Valida con el usuario**

**Ejemplo - Proceso de facturación:**
```
Actor: Departamento administrativo

1. `El departamento administrativo recibe parte de trabajo`
2. `El departamento administrativo revisa datos del cliente`
3. `El departamento administrativo calcula costes`
4. `El departamento administrativo crea factura`
5. `El departamento administrativo envía factura`

Actor: Cliente

6. `El cliente recibe factura`
7. `El cliente revisa factura`
8. `El cliente aprueba factura`
```

**Validación:** "¿El departamento envía la factura antes o después de crearla?"

---

## Validación de Secuencias

### Preguntas para Validar Orden

**Para eventos:**
- "¿El evento X ocurre antes o después del evento Y?"
- "¿Puede ocurrir Y sin que haya ocurrido X primero?"
- "¿Hay algún paso entre X e Y que falte?"

**Para causalidad:**
- "¿Qué causa que ocurra Y?"
- "¿X es prerequisito de Y?"
- "¿Y depende de que X haya ocurrido?"

**Para tiempo:**
- "¿Cuánto tiempo pasa entre X e Y?"
- "¿X e Y pueden ocurrir simultáneamente?"
- "¿Y ocurre inmediatamente después de X?"

### Checklist de Validación

**Para cada paso N:**
- [ ] ¿Tiene sentido que ocurra después del paso N-1?
- [ ] ¿Es prerequisito para el paso N+1?
- [ ] ¿Hay algún paso intermedio faltante?
- [ ] ¿El actor puede hacer esto en este momento?
- [ ] ¿El objeto de trabajo está disponible?

### Ejemplo de Validación Completa

**Historia propuesta:**
1. `El empleado solicita vacaciones`
2. `El supervisor aprueba vacaciones`
3. `El sistema actualiza calendario`
4. `El empleado recibe confirmación`

**Validación paso a paso:**

**Paso 1 → Paso 2:**
- ¿Puede el supervisor aprobar antes de que el empleado solicite? ❌ No
- ¿Falta algún paso? 🤔 ¿Y si hay validación de días disponibles?

**Historia refinada:**
1. `El empleado solicita vacaciones`
2. `El sistema valida días disponibles`
3. `El supervisor aprueba vacaciones`
4. `El sistema actualiza calendario`
5. `El empleado recibe confirmación`

---

## Errores Comunes en Numeración

### Error 1: Saltos Lógicos

**❌ Problema:**
```
1. `El cliente solicita presupuesto`
2. `El cliente firma contrato` (¡saltó 5 pasos!)
```

**✅ Solución:**
```
1. `El cliente solicita presupuesto`
2. `El vendedor prepara presupuesto`
3. `El vendedor envía presupuesto`
4. `El cliente recibe presupuesto`
5. `El cliente aprueba presupuesto`
6. `El vendedor prepara contrato`
7. `El cliente firma contrato`
```

### Error 2: Números Duplicados o Perdidos

**❌ Problema:**
```
1. `Usuario hace X`
2. `Sistema hace Y`
2. `Usuario hace Z` (¡número duplicado!)
4. `Sistema hace W` (¡saltó el 3!)
```

**✅ Solución:**
```
1. `Usuario hace X`
2. `Sistema hace Y`
3. `Usuario hace Z`
4. `Sistema hace W`
```

### Error 3: Acciones Simultáneas

**❌ Problema:**
```
1. `Usuario hace X`
2. `Sistema hace Y al mismo tiempo` (¿qué va primero?)
```

**✅ Solución:**
```
1. `Usuario hace X`
2. `Sistema detecta X`
3. `Sistema hace Y` (o viceversa, según sea el orden real)
```

### Error 4: Orden por Importancia vs. Tiempo

**❌ Problema:**
```
1. `Acción importante`
2. `Acción menor`
3. `Acción importante` (orden por importancia, no tiempo)
```

**✅ Solución:**
```
1. `Acción que ocurre primero`
2. `Acción que ocurre segundo`
3. `Acción que ocurre tercero` (orden cronológico)
```

---

## Ejemplos Completos Numerados

### Ejemplo 1: Proceso de Contratación

```
Historia: Contratación de nuevo empleado

1. `El departamento identifica necesidad de personal`
2. `RRHH publica oferta de empleo`
3. `Candidatos envían currículums`
4. `Sistema ATS registra aplicaciones`
5. `Recruiter revisa currículums`
6. `Recruiter selecciona candidatos preseleccionados`
7. `RRHH programa entrevistas`
8. `Candidatos asisten a entrevistas`
9. `Entrevistadores evalúan candidatos`
10. `RRHH selecciona candidato final`
11. `RRHH prepara contrato`
12. `Candidato elegido firma contrato`
13. `RRHH registra empleado en sistema`
14. `RRHH programa jornada de formación`

Validación: ¿Puede RRHH registrar al empleado antes de que firme el contrato? No. ✓
```

### Ejemplo 2: Proceso de Órdenes de Trabajo

```
Historia: Creación y ejecución de orden de trabajo

1. `Cliente solicita servicio`
2. `Departamento comercial recibe solicitud`
3. `Departamento comercial crea orden preliminar`
4. `Responsable de operaciones revisa orden`
5. `Responsable de operaciones asigna técnico`
6. `Técnico recibe orden`
7. `Técnico se desplaza al lugar`
8. `Técnico realiza el servicio`
9. `Técnico completa parte de trabajo`
10. `Cliente firma conformidad`
11. `Sistema calcula costes automáticamente`
12. `Departamento administrativo crea factura`
13. `Departamento administrativo envía factura`
14. `Cliente recibe factura`

Validación: ¿Puede el sistema calcular costes antes de que el técnico complete el trabajo? No. ✓
```

### Ejemplo 3: Proceso de Control de Calidad

```
Historia: Control de calidad de productos

1. `Producto llega al área de calidad`
2. `Inspector recibe producto`
3. `Inspector verifica identificación del producto`
4. `Inspector realiza pruebas según protocolo`
5. `Inspector compara resultados con estándares`
6. `Producto cumple estándares`
7. `Inspector etiqueta producto como APROBADO`
8. `Inspector registra resultado en sistema`
9. `Producto se envía a almacén`
10. `Almacén recibe producto aprobado`

Validación: ¿Puede el inspector etiquetar antes de realizar pruebas? No. ✓
```

---

## Técnicas Avanzadas

### Numeración con Sub-pasos

**Cuando una acción tiene componentes internos:**

```
Historia: Validación de datos de empleado

1. `RRHH recibe documentación de empleado`
2. `RRHH valida documentación completa`
   2.1. `Verifica que incluye DNI`
   2.2. `Verifica que incluye certificado de estudios`
   2.3. `Verifica que incluye referencias laborales`
3. `RRHH acepta documentación`
```

**Nota:** Los sub-pasos (2.1, 2.2, 2.3) ocurren TODOS como parte del paso 2.

### Numeración con Hilos Paralelos

**Cuando dos actores actúan en paralelo:**

```
Historia: Preparación de evento

Actor A (Organizador):
1. `Organizador contrata lugar`
2. `Organizador invita participantes`
3. `Organizador prepara material`

Actor B (Catering):
1. `Catering recibe solicitud`
2. `Catering prepara menú`
3. `Catering confirma asistencia`

Punto de sincronización:
4. `Organizador confirma que todo está listo`
5. `Evento se realiza`
```

### Numeración por Roles

**Cuando el mismo actor aparece múltiples veces:**

```
Historia: Gestión de vacaciones

Mismo actor (Empleado):
1. `Empleado solicita vacaciones`
2. `Empleado recibe aprobación`
3. `Empleado disfruta vacaciones`
4. `Empleado regresa al trabajo`

Validación: ¿Puede el empleado regresar antes de disfrutar vacaciones? No. ✓
```

---

## Herramientas de Apoyo

### Checklist Durante la Captura

**Mientras el usuario narra:**
- [ ] ¿Estoy asignando números consecutivos?
- [ ] ¿El orden refleja tiempo real?
- [ ] ¿Cada número = una acción?
- [ ] ¿Un actor por número?
- [ ] ¿Hay saltos lógicos?
- [ ] ¿El paso N lleva al N+1?

### Preguntas de Recuperación

**Cuando el usuario se detiene:**
- "¿Qué pasa después?"
- "¿Antes o después de esto?"
- "¿Quién hace esto?"
- "¿Cuándo ocurre exactamente?"
- "¿Qué paso viene después?"

### Frases de Validación

**Para confirmar secuencia:**
- "Vamos a verificar el orden..."
- "¿Puede pasar X antes que Y?"
- "¿Hay algo entre estos dos pasos?"
- "¿El paso 3 va antes o después del 4?"
- "¿Esto ocurre inmediatamente después?"

---

## Resumen: Reglas de Numeración

### Reglas de Oro

1. **Consecutividad estricta** - Sin números perdidos
2. **Orden temporal** - El número refleja tiempo, no importancia
3. **Una acción por número** - Cada número = una sola acción
4. **Un actor por número** - Un actor principal por paso
5. **Progresión lógica** - Cada paso lleva al siguiente
6. **Validación constante** - "¿Antes o después?"

### Señales de Alerta

❌ **Saltos en numeración** (1, 3, 5...)
❌ **Orden por importancia** (importante primero)
❌ **Múltiples acciones** por número
❌ **Múltiples actores** por número
❌ **Saltos lógicos** (falta de pasos intermedios)
❌ **Causalidad confusa** (X no causa Y)

### Frases de Ayuda

✅ **"¿Qué pasa después?"**
✅ **"¿Antes o después de esto?"**
✅ **"¿Puede ocurrir Y sin X?"**
✅ **"¿Hay algo entre X e Y?"**
✅ **"Verifiquemos el orden..."**
✅ **"El número refleja tiempo, no importancia"**

**Recuerda:** La numeración secuencial es el esqueleto de tu historia. Sin un orden claro, la historia se desploma. Cada número cuenta, cada orden importa.