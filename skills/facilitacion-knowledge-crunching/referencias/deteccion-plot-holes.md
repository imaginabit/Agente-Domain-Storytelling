# Detección de Plot Holes (Huecos de la Trama)

Este documento contiene casos reales y metodologías para identificar gaps lógicos en historias de Domain Storytelling, asegurando que cada transición tenga sentido y esté documentada.

## ¿Qué son los Plot Holes?

Los **Plot Holes** o huecos de la trama son omisiones lógicas en una narrativa donde se asume que algo ocurre sin explicar cómo o por qué. Son "saltos" en la historia que el experto del dominio da por sentado pero que son pasos reales en el proceso.

### Características de un Plot Hole:
- ❌ **Transición no explicada** - Se asume que algo "pasa automáticamente"
- ❌ **Información faltante** - No se menciona qué datos se usan
- ❌ **Causalidad no establecida** - X ocurre, luego Y, sin conexión
- ❌ **Comunicación implícita** - Alguien se entera sin que se explique cómo
- ❌ **Validación omitida** - Se asume que algo es correcto sin verificar

---

## Tipos de Plot Holes

### 1. Plot Holes de Comunicación

**Definición:** Un actor recibe o envía información sin explicar el mecanismo

#### Ejemplo 1: Solicitud de Vacaciones

**Historia original:**
```
1. `El empleado solicita vacaciones`
2. `El supervisor aprueba`
3. `El empleado disfruta vacaciones`
```

**Plot hole detectado:**
- Entre paso 2 y 3: ¿Cómo se entera el empleado que fue aprobada?

**Preguntas para detectar:**
- "¿Cómo se entera [actor] de [evento]?"
- "¿Qué medio usa para comunicar [información]?"
- "¿[actor] recibe notificación automática?"

**Historia corregida:**
```
1. `El empleado solicita vacaciones`
2. `El supervisor aprueba la solicitud`
3. `El sistema envía email de aprobación`
4. `El empleado recibe la notificación`
5. `El empleado disfruta las vacaciones`
```

#### Ejemplo 2: Orden de Compra

**Historia original:**
```
1. `El departamento de compras genera orden`
2. `El proveedor recibe la orden`
3. `El proveedor prepara el envío`
```

**Plot hole detectado:**
- Entre paso 1 y 2: ¿Cómo recibe el proveedor la orden?

**Historia corregida:**
```
1. `El departamento de compras genera orden de compra`
2. `El sistema envía email con orden al proveedor`
3. `El proveedor recibe el email`
4. `El proveedor revisa la orden`
5. `El proveedor prepara el envío`
```

#### Ejemplo 3: Facturación

**Historia original:**
```
1. `El técnico completa la orden`
2. `El cliente recibe la factura`
```

**Plot hole detectado:**
- Múltiples gaps: ¿Cómo se genera la factura? ¿Qué datos usa? ¿Cómo se envía?

**Historia corregida:**
```
1. `El técnico completa la orden`
2. `El técnico genera parte de trabajo`
3. `El sistema calcula costes automáticamente`
4. `El departamento administrativo crea factura`
5. `El departamento administrativo envía factura por email`
6. `El cliente recibe la factura`
```

---

### 2. Plot Holes de Validación

**Definición:** Se actúa sobre información sin verificar que sea correcta

#### Ejemplo 1: Registro de Cliente

**Historia original:**
```
1. `El cliente proporciona sus datos`
2. `El sistema crea la cuenta`
3. `El cliente puede usar el servicio`
```

**Plot hole detectado:**
- Paso 1 → 2: ¿Se validan los datos? ¿Qué pasa si hay errores?

**Preguntas para detectar:**
- "¿Cómo saben que los datos son correctos?"
- "¿Se verifica [información específica]?"
- "¿Qué pasa si la información es incorrecta?"

**Historia corregida:**
```
1. `El cliente proporciona sus datos`
2. `El sistema valida los datos`
   2.1. `Verifica formato de email`
   2.2. `Verifica que el email no existe`
   2.3. `Valida teléfono`
3. `Si los datos son válidos: El sistema crea la cuenta`
4. `Si los datos son inválidos: El sistema muestra errores`
5. `El cliente puede usar el servicio`
```

#### Ejemplo 2: Aprobación de Presupuesto

**Historia original:**
```
1. `El vendedor prepara presupuesto`
2. `El cliente aprueba el presupuesto`
3. `Se procede con la venta`
```

**Plot hole detectado:**
- ¿Cómo sabe el cliente que el presupuesto es correcto? ¿Se incluye desglose? ¿Precios finales?

**Historia corregida:**
```
1. `El vendedor prepara presupuesto detallado`
2. `El vendedor envía presupuesto al cliente`
3. `El cliente recibe el presupuesto`
4. `El cliente revisa el presupuesto`
5. `El cliente aprueba el presupuesto`
6. `Se procede con la venta`
```

---

### 3. Plot Holes de Transición de Estado

**Definición:** Un objeto cambia de estado sin una acción que lo cause

#### Ejemplo 1: Orden de Trabajo

**Historia original:**
```
1. `Se crea la orden de trabajo`
2. `La orden está en progreso`
3. `La orden está completada`
```

**Plot hole detectado:**
- ¿Cómo cambia la orden de estado? ¿Quién actualiza el estado?

**Preguntas para detectar:**
- "¿Qué causa que cambie de [estado A] a [estado B]?"
- "¿Quién actualiza el estado?"
- "¿Cómo se registra el cambio de estado?"

**Historia corregida:**
```
1. `Se crea la orden de trabajo (estado: CREADA)`
2. `El responsable asigna técnico (estado: ASIGNADA)`
3. `El técnico inicia el trabajo (estado: EN PROGRESO)`
4. `El técnico completa el trabajo (estado: COMPLETADA)`
```

#### Ejemplo 2: Solicitud de Empleado

**Historia original:**
```
1. `El empleado solicita formación`
2. `La solicitud está aprobada`
3. `El empleado asiste al curso`
```

**Plot hole detectado:**
- ¿Quién aprueba? ¿Cómo se actualiza el estado? ¿Qué criterios se usan?

**Historia corregida:**
```
1. `El empleado solicita formación`
2. `El supervisor recibe la solicitud`
3. `El supervisor evalúa la solicitud`
4. `El supervisor aprueba la solicitud`
5. `El sistema actualiza estado a APROBADA`
6. `El empleado recibe notificación de aprobación`
7. `El empleado asiste al curso`
```

---

### 4. Plot Holes de Sistemas Intermedios

**Definición:** Se usa información de un sistema sin explicar cómo se transfiere

#### Ejemplo 1: Tablet a Sistema

**Historia original:**
```
1. `El técnico completa la orden en el tablet`
2. `El administrativo ve los datos en el sistema`
```

**Plot hole detectado:**
- ¿Cómo viajan los datos del tablet al sistema? ¿Se sincronizan automáticamente?

**Preguntas para detectar:**
- "¿Cómo se transfieren los datos de [sistema A] a [sistema B]?"
- "¿Hay sincronización automática?"
- "¿Qué pasa si no hay conexión?"

**Historia corregida:**
```
1. `El técnico completa la orden en el tablet`
2. `El técnico guarda los datos`
3. `El tablet sincroniza con el servidor`
4. `El sistema actualiza la base de datos`
5. `El administrativo consulta la orden en el sistema`
```

#### Ejemplo 2: Múltiples Sistemas

**Historia original:**
```
1. `El vendedor registra la venta`
2. `El sistema de contabilidad contabiliza`
3. `El sistema de inventario descuenta productos`
```

**Plot hole detectado:**
- ¿Cómo se comunican los sistemas? ¿En qué orden? ¿Qué pasa si uno falla?

**Historia corregida:**
```
1. `El vendedor registra la venta`
2. `El sistema valida la venta`
3. `El sistema envía evento a sistemas integrados`
   3.1. `Sistema de contabilidad recibe evento`
   3.2. `Sistema de inventario recibe evento`
4. `Sistema de contabilidad contabiliza la venta`
5. `Sistema de inventario descuenta productos`
```

---

### 5. Plot Holes de Información Faltante

**Definición:** Se actúa con información que no se mencionó

#### Ejemplo 1: Cálculo de Precio

**Historia original:**
```
1. `El cliente solicita presupuesto`
2. `El vendedor prepara el precio`
3. `El cliente recibe el presupuesto`
```

**Plot hole detectado:**
- ¿Qué información usa para calcular el precio? ¿Tarifas? ¿Descuentos? ¿Impuestos?

**Preguntas para detectar:**
- "¿Con qué información cuenta [actor] para hacer [acción]?"
- "¿Qué datos necesita para [tarea]?"
- "¿De dónde viene esa información?"

**Historia corregida:**
```
1. `El cliente solicita presupuesto`
2. `El vendedor consulta tarifa base`
3. `El vendedor verifica descuentos aplicables`
4. `El vendedor calcula impuestos`
5. `El vendedor prepara presupuesto detallado`
6. `El cliente recibe el presupuesto`
```

#### Ejemplo 2: Disponibilidad de Técnico

**Historia original:**
```
1. `Llega orden de trabajo`
2. `Se asigna un técnico`
3. `El técnico va al lugar`
```

**Plot hole detectado:**
- ¿Cómo se sabe qué técnicos están disponibles? ¿Qué criterios se usan para asignar?

**Historia corregida:**
```
1. `Llega orden de trabajo`
2. `El responsable consulta disponibilidad de técnicos`
3. `El responsable identifica técnicos disponibles`
4. `El responsable evalúa técnicos según criterios`
5. `El responsable asigna técnico específico`
6. `El técnico recibe la orden`
7. `El técnico va al lugar`
```

---

## Metodología para Detectar Plot Holes

### Paso 1: Escucha Secuencial
**Proceso:**
1. Escucha la historia completa sin interrumpir
2. Toma notas de cada paso
3. Identifica puntos donde algo se "da por sentado"
4. Marca transiciones que parecen "saltos"

### Paso 2: Preguntas de Conexión
**Para cada transición entre pasos X → Y:**

- **Pregunta de causalidad:**
  - "¿Qué causa que pase Y después de X?"
  - "¿X es prerequisito de Y?"

- **Pregunta de mecanismo:**
  - "¿Cómo ocurre exactamente la transición?"
  - "¿Qué mecanismo permite que pase Y?"

- **Pregunta de información:**
  - "¿Qué información se necesita para Y?"
  - "¿De dónde viene esa información?"

- **Pregunta de actor:**
  - "¿Quién hace que pase Y?"
  - "¿Qué actor es responsable de Y?"

### Paso 3: Validación de Causalidad
**Para cada "X → Y":**

```
❌ Causalidad débil:
"X ocurre, luego Y ocurre" (no se explica la relación)

✅ Causalidad fuerte:
"X ocurre, esto causa Y" (relación clara)
```

**Ejemplos:**
```
❌ "El supervisor aprueba, luego el empleado se va de vacaciones"
✅ "El supervisor aprueba, envía notificación al empleado, quien entonces puede irse"

❌ "Se genera la factura, luego el cliente paga"
✅ "Se genera la factura, se envía al cliente, quien revisa y paga"
```

### Paso 4: Identificación de Implícitos
**¿Qué se asume pero no se dice?**

| Asumido implícitamente | Pregunta para detectar |
|------------------------|------------------------|
| "El sistema envía" | ¿Por qué medio? ¿Email? ¿SMS? |
| "Se valida" | ¿Cómo? ¿Qué criterios? |
| "Automáticamente" | ¿Qué proceso automático? |
| "Se actualiza" | ¿Por quién? ¿En qué sistema? |
| "Se comunica" | ¿Quién habla con quién? |

---

## Ejemplos Completos de Detección

### Ejemplo 1: Proceso de Contratación

#### Historia Original (con múltiples plot holes)
```
1. `RRHH publica oferta`
2. `Candidatos envían CVs`
3. `RRHH revisa CVs`
4. `Se selecciona candidato`
5. `El candidato firma contrato`
6. `El empleado empieza a trabajar`
```

#### Plot Holes Detectados

**Plot Hole 1:** Comunicación de oferta
- Gap: ¿Cómo llegan las aplicaciones a RRHH?
- Pregunta: "¿Cómo reciben las aplicaciones?"

**Plot Hole 2:** Proceso de selección
- Gap: ¿Qué criterios se usan para seleccionar?
- Pregunta: "¿Cómo se decide quién es seleccionado?"

**Plot Hole 3:** Firma de contrato
- Gap: ¿Cómo se entrega el contrato? ¿Dónde firma?
- Pregunta: "¿Cómo firma el candidato? ¿Presencial? ¿Digital?"

**Plot Hole 4:** Inicio de trabajo
- Gap: ¿Qué pasa entre firmar y empezar? ¿Hay formación? ¿Papeleo?
- Pregunta: "¿Qué actividades ocurren entre firma y primer día?"

#### Historia Corregida
```
1. `RRHH publica oferta en portal de empleo`
2. `Candidatos envían CVs vía formulario web`
3. `Sistema ATS registra aplicaciones`
4. `RRHH revisa CVs según criterios`
   4.1. `Verifica experiencia mínima`
   4.2. `Evalúa formación`
   4.3. `Revisa referencias`
5. `RRHH selecciona candidatos para entrevista`
6. `RRHH envía convocatoria de entrevista`
7. `Candidatos asisten a entrevistas`
8. `Entrevistadores evalúan candidatos`
9. `RRHH selecciona candidato final`
10. `RRHH prepara contrato laboral`
11. `RRHH envía contrato al candidato`
12. `Candidato firma contrato digitalmente`
13. `RRHH programa jornada de onboarding`
14. `Empleado recibe credenciales de acceso`
15. `Empleado empieza a trabajar`
```

---

### Ejemplo 2: Proceso de Facturación

#### Historia Original (con plot holes)
```
1. `Técnico termina orden`
2. `Se genera factura`
3. `Cliente recibe factura`
4. `Cliente paga factura`
```

#### Plot Holes Detectados

**Plot Hole 1:** Generación de factura
- Gap: ¿Qué datos usa? ¿Cómo se calcula?
- Pregunta: "¿Qué información incluye la factura?"

**Plot Hole 2:** Envío de factura
- Gap: ¿Por qué medio? ¿Cuándo?
- Pregunta: "¿Cómo llega la factura al cliente?"

**Plot Hole 3:** Proceso de pago
- Gap: ¿Cómo paga? ¿Qué métodos acepta?
- Pregunta: "¿Qué opciones de pago tiene el cliente?"

#### Historia Corregida
```
1. `Técnico termina orden de trabajo`
2. `Técnico genera parte de trabajo detallado`
3. `Sistema calcula costes automáticamente`
   3.1. `Suma horas de trabajo`
   3.2. `Añade coste de materiales`
   3.3. `Calcula impuestos`
4. `Departamento administrativo crea factura`
5. `Departamento administrativo revisa factura`
6. `Departamento administrativo envía factura por email`
7. `Cliente recibe factura`
8. `Cliente revisa factura`
9. `Cliente selecciona método de pago`
   9.1. `Tarjeta de crédito`
   9.2. `Transferencia bancaria`
   9.3. `PayPal`
10. `Cliente completa el pago`
11. `Sistema confirma recepción de pago`
12. `Sistema envía recibo al cliente`
```

---

### Ejemplo 3: Proceso de Control de Calidad

#### Historia Original (con plot holes)
```
1. `Producto llega a calidad`
2. `Inspector verifica producto`
3. `Producto se aprueba`
4. `Producto va a almacén`
```

#### Plot Holes Detectados

**Plot Hole 1:** Proceso de verificación
- Gap: ¿Qué pruebas se hacen? ¿Qué criterios?
- Pregunta: "¿Cómo verifica que cumple estándares?"

**Plot Hole 2:** Etiquetado
- Gap: ¿Cómo se marca que está aprobado?
- Pregunta: "¿Cómo se registra la aprobación?"

**Plot Hole 3:** Transferencia a almacén
- Gap: ¿Cómo se comunica a almacén? ¿Con qué documentación?
- Pregunta: "¿Cómo sabe almacén que puede recibirlo?"

#### Historia Corregida
```
1. `Producto llega al área de calidad`
2. `Inspector recibe producto`
3. `Inspector identifica producto`
4. `Inspector realiza pruebas según protocolo`
   4.1. `Prueba de funcionalidad`
   4.2. `Prueba de resistencia`
   4.3. `Prueba de apariencia`
5. `Inspector compara resultados con estándares`
6. `Producto cumple todos los criterios`
7. `Inspector etiqueta producto como APROBADO`
8. `Inspector registra resultado en sistema`
9. `Sistema notifica a almacén`
10. `Almacén recibe notificación de aprobación`
11. `Producto se traslada a almacén`
12. `Almacén registra recepción`
```

---

## Errores Comunes en Detección

### Error 1: No Preguntar Suficientemente
❌ **Problema:** Aceptar "automáticamente" sin entender el proceso
```
"El sistema calcula automáticamente"
❌ (no profundizar)

"El sistema calcula automáticamente"
✅ "¿Cómo calcula exactamente? ¿Qué fórmula usa?"
```

### Error 2: Asumir Conocimiento Común
❌ **Problema:** Dar por sentado que "todos saben cómo funciona"
```
"Luego se envía al cliente"
❌ (asumir que se sabe cómo)

"Luego se envía al cliente"
✅ "¿Por qué medio? ¿Email? ¿Correo postal?"
```

### Error 3: No Validar Transiciones
❌ **Problema:** No verificar que X realmente cause Y
```
"Después de aprobar, el empleado se va"
❌ (no validar causalidad)

"Después de aprobar, el empleado se va"
✅ "¿Qué pasa entre aprobar y irse? ¿Se entera automáticamente?"
```

### Error 4: Mezclar Múltiples Gaps
❌ **Problema:** Intentar arreglar todo de una vez
```
1. "El empleado solicita vacaciones"
2. "El supervisor aprueba y envía email y empleado recibe y disfruta"
❌ (demasiados pasos en uno)

1. "El empleado solicita vacaciones"
2. "El supervisor aprueba"
3. "Sistema envía email"
4. "Empleado recibe"
5. "Empleado disfruta"
✅ (un paso a la vez)
```

---

## Checklist para Detección

### Durante la Sesión

**Para cada paso N → N+1:**
- [ ] ¿Qué causa que pase N+1?
- [ ] ¿Cómo ocurre la transición?
- [ ] ¿Qué información se necesita?
- [ ] ¿Quién es responsable?
- [ ] ¿Qué medio/mecanismo se usa?

**Señales de alerta:**
- [ ] "Automáticamente" sin explicar cómo
- [ ] "Luego..." sin explicar qué pasa en el medio
- [ ] "Se actualiza" sin decir quién actualiza
- [ ] "Se comunica" sin decir cómo
- [ ] "Se valida" sin decir cómo

### Preguntas de Oro

1. **"¿Cómo exactamente...?"**
   - "¿Cómo exactamente se entera X de Y?"
   - "¿Cómo exactamente se calcula...?"

2. **"¿Qué pasa entre...?"**
   - "¿Qué pasa entre que aprueba y que se va?"
   - "¿Qué pasa entre generar y enviar?"

3. **"¿De dónde viene...?"**
   - "¿De dónde viene esa información?"
   - "¿De dónde sale ese dato?"

4. **"¿Quién hace que...?"**
   - "¿Quién hace que cambie el estado?"
   - "¿Quién es responsable de...?"

---

## Resumen: Plot Holes vs. Happy Path

| Aspecto | Plot Hole (Problemático) | Historia Completa (Correcto) |
|---------|-------------------------|-------------------------------|
| **Transiciones** | Implícitas | Explícitas |
| **Información** | Asumida | Documentada |
| **Causalidad** | No establecida | Clara |
| **Comunicación** | "Se comunica" | Detalle del medio |
| **Validación** | Asumida | Proceso detallado |
| **Estados** | Cambios mágicos | Acciones que causan cambio |

**Regla de oro:** Si algo "pasa automáticamente", pregunta "¿cómo?" Si algo "se actualiza", pregunta "¿quién?" Si algo "se comunica", pregunta "¿por qué medio?"

**Recuerda:** No hay conocimiento común. Lo que es obvio para el experto del dominio puede ser un misterio para todos los demás. Siempre pregunta, siempre clarifica, nunca asumas.
