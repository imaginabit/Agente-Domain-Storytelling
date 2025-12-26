# Eliminación de Condicionales

Este documento detalla técnicas para evitar estructuras if/else y gateways en las narrativas de Domain Storytelling, creando historias lineales y fáciles de seguir.

## ¿Por qué Eliminar Condicionales?

### Problemas con Condicionales en Historias
❌ **Complejidad excesiva** - Las ramas multiplican la complejidad
❌ **Difícil de seguir** - El lector pierde el hilo narrativo
❌ **Complejo de modelar** - Software con muchas ramas es difícil
❌ **Estado inconsistente** - Múltiples paths pueden llevar a errores
❌ **Testing complejo** - Cada rama requiere tests separados

### Beneficios de Historias Lineales
✅ **Fácil de entender** - Un solo camino a seguir
✅ **Fácil de modelar** - Software más simple
✅ **Fácil de implementar** - Flujo directo
✅ **Fácil de testear** - Un camino = un test
✅ **Fácil de mantener** - Menos puntos de fallo

---

## Identificación de Condicionales

### Tipos de Condicionales Comunes

#### 1. Condicionales Explícitos
**Frases típicas:**
- "Si... entonces..."
- "Si... si no..."
- "Cuando... si..."
- "En caso de que..."
- "A menos que..."

**Ejemplos:**
- "Si el cliente tiene crédito, aprobamos la venta"
- "Si el stock está disponible, enviamos el pedido"
- "A menos que sea emergencia, seguimos el protocolo"

#### 2. Condicionales Implícitos
**Frases típicas:**
- "Dependiendo de..."
- "Según..."
- "Puede ser que..."
- "Hay veces que..."
- "En ocasiones..."

**Ejemplos:**
- "Dependiendo del tipo de cliente, aplicamos descuentos"
- "Según la urgencia, priorizamos la orden"
- "Hay veces que rechazamos la solicitud"

#### 3. Múltiples Ramas
**Frases típicas:**
- "Si A, entonces X; si B, entonces Y; si C, entonces Z"
- "O bien... o bien..."
- "Bien sea... o sea..."

**Ejemplos:**
- "Si es cliente premium, envío gratis; si es normal, costo adicional; si es nuevo, descuento"
- "O bien lo hace X, o bien lo hace Y"

---

## Técnicas de Eliminación

### Técnica 1: Captura del Camino Principal

**Cuándo usar:** Cuando hay un "camino dorado" (80% de casos)

**Proceso:**
1. **Identifica la condición**
2. **Pregunta por el caso normal**
3. **Captura solo ese caso**
4. **Documenta variaciones como historias separadas**

**Ejemplo:**
```
Narrativa original:
"Si el empleado tiene días disponibles, apruebo vacaciones; si no, las rechazo."

Aplicando técnica:
Tú: "¿En el caso normal, el empleado tiene días disponibles?"
Usuario: "Sí, normalmente sí."
Tú: "Perfecto, entonces sigamos con ese caso."

Happy path:
1. `El empleado solicita vacaciones`
2. `El empleado tiene días disponibles`
3. `El supervisor aprueba vacaciones`

Variación:
1. `El empleado solicita vacaciones`
2. `El empleado NO tiene días disponibles`
3. `El supervisor rechaza vacaciones`
```

### Técnica 2: División en Historias Separadas

**Cuándo usar:** Cuando hay múltiples alternativas importantes

**Proceso:**
1. **Identifica cada rama como historia independiente**
2. **Numera cada historia separadamente**
3. **Relaciona las historias entre sí**
4. **Mantiene cada una lineal**

**Ejemplo:**
```
Narrativa original:
"Si el pago es con tarjeta, proceso automáticamente; si es transferencia, espero confirmación; si es efectivo, emito recibo."

División en historias:

Historia A (Principal - más común):
1. `El cliente elige pago con tarjeta`
2. `El sistema procesa el pago automáticamente`
3. `El sistema confirma el pago`
4. `El sistema emite factura`

Historia B:
1. `El cliente elige pago por transferencia`
2. `El sistema solicita comprobante de transferencia`
3. `El cliente envía comprobante`
4. `El sistema verifica y confirma`
5. `El sistema emite factura`

Historia C:
1. `El cliente elige pago en efectivo`
2. `El sistema emite recibo de pago`
3. `El cliente paga en efectivo`
4. `El sistema confirma recepción`
5. `El sistema emite factura`
```

### Técnica 3: Estados como Objetos de Trabajo

**Cuándo usar:** Cuando el "estado" cambia según condiciones

**Proceso:**
1. **Identifica los estados posibles**
2. **Modela cada estado como objeto**
3. **Las transiciones entre estados son pasos**
4. **Cada historia = una secuencia de estados**

**Ejemplo:**
```
Narrativa original:
"La solicitud puede estar: pendiente, en revisión, aprobada o rechazada. Si está pendiente, va a revisión. Si está en revisión y cumple criterios, se aprueba. Si no cumple, se rechaza."

Aplicando técnica:

Historia A (Flujo de aprobación):
1. `La solicitud se crea` (estado: PENDIENTE)
2. `La solicitud pasa a estado EN REVISIÓN`
3. `El revisor evalúa la solicitud`
4. `La solicitud cumple criterios`
5. `La solicitud pasa a estado APROBADA`

Historia B (Flujo de rechazo):
1. `La solicitud se crea` (estado: PENDIENTE)
2. `La solicitud pasa a estado EN REVISIÓN`
3. `El revisor evalúa la solicitud`
4. `La solicitud NO cumple criterios`
5. `La solicitud pasa a estado RECHAZADA`

Historia C (Flujo de revisión):
1. `La solicitud está en estado EN REVISIÓN`
2. `El revisor revisa la solicitud`
3. `El revisor completa la evaluación`
```

### Técnica 4: Secuencias de Validación

**Cuándo usar:** Cuando hay múltiples validaciones en secuencia

**Proceso:**
1. **Identifica cada validación como paso**
2. **Cada validación exitosa = un paso**
3. **Las fallas van a historia separada**
4. **Mantiene la lógica de negocio clara**

**Ejemplo:**
```
Narrativa original:
"El sistema valida: si el usuario existe, entonces valida crédito; si el crédito es suficiente, entonces procesa; si no, rechaza."

Aplicando técnica:

Historia A (Validación exitosa):
1. `El usuario ingresa al sistema`
2. `El sistema valida que el usuario existe`
3. `El sistema valida que el usuario tiene crédito`
4. `El sistema procesa la solicitud`
5. `El sistema confirma el procesamiento`

Historia B (Usuario no existe):
1. `El usuario ingresa al sistema`
2. `El sistema valida que el usuario existe`
3. `El sistema detecta que el usuario NO existe`
4. `El sistema rechaza el acceso`

Historia C (Crédito insuficiente):
1. `El usuario ingresa al sistema`
2. `El sistema valida que el usuario existe`
3. `El sistema valida que el usuario tiene crédito`
4. `El sistema detecta que el crédito es insuficiente`
5. `El sistema rechaza la solicitud`
```

### Técnica 5: Eventos Temporales

**Cuándo usar:** Cuando las condiciones dependen del tiempo

**Proceso:**
1. **Identifica eventos disparadores**
2. **Cada evento = inicio de una historia**
3. **Evita "si después de X tiempo"**
4. **Modela como historias independientes**

**Ejemplo:**
```
Narrativa original:
"Cuando llega el pedido, si es urgente, lo procesamos inmediatamente; si no, va a cola normal. Si no se procesa en 24h, enviamos alerta."

Aplicando técnica:

Historia A (Pedido urgente):
1. `Llega pedido marcado como urgente`
2. `El sistema procesa el pedido inmediatamente`
3. `El sistema completa el pedido`

Historia B (Pedido normal):
1. `Llega pedido normal`
2. `El sistema añade el pedido a la cola`
3. `El sistema procesa pedidos de la cola en orden`
4. `El sistema completa el pedido`

Historia C (Alerta por demora):
1. `El pedido está en la cola`
2. `El sistema detecta que han pasado 24 horas`
3. `El sistema envía alerta de demora`
```

---

## Redirecciones para Eliminar Condicionales

### Frases para Detener Condicionales

**Cuando el usuario dice "Si...":**
- "Espera, hablemos primero del caso más común"
- "¿Qué pasa normalmente, sin condiciones?"
- "¿En el 80% de casos?"
- "Redirigamos al camino principal"

**Cuando el usuario dice "Dependiendo de...":**
- "¿Cuál es el caso más típico?"
- "¿Qué sucede la mayoría de veces?"
- "¿Cuál es el escenario ideal?"
- "Empecemos por el caso más frecuente"

**Cuando el usuario dice "A veces...":**
- "Anoto eso para después. ¿Qué pasa normalmente?"
- "¿En el caso ideal?"
- "Sigamos el 80% de casos primero"
- "Esa va a ser una historia separada"

### Preguntas de Clarificación

**Para entender el happy path:**
- "¿Cuál es el caso normal?"
- "¿Qué ocurre la mayoría de veces?"
- "¿Cómo funciona sin complicaciones?"
- "¿Cuál es el flujo ideal?"

**Para identificar variaciones:**
- "¿Eso es común o excepcional?"
- "¿Con qué frecuencia ocurre?"
- "¿Es el 80% o el 20%?"
- "¿Qué porcentaje de casos?"

---

## Ejemplos Completos de Eliminación

### Ejemplo 1: Proceso de Registro de Usuario

#### Narrativa Original (con condicionales)
```
"Cuando alguien se registra, verifica el email. Si el email es válido, envía confirmación. Si no, muestra error. Si el usuario confirma, activa la cuenta. Si no confirma en 24h, elimina el registro. A veces si el usuario es corporativo, se asigna automáticamente."
```

#### Condicionales Identificados
1. "Si el email es válido..." → rama de validación
2. "Si el usuario confirma..." → rama de activación
3. "Si no confirma en 24h..." → rama de expiración
4. "A veces si el usuario es corporativo..." → rama especial

#### Historias Separadas (Sin Condicionales)

**Historia A (Registro estándar - Happy Path):**
1. `El usuario completa el formulario de registro`
2. `El usuario ingresa un email válido`
3. `El sistema valida el email`
4. `El sistema envía email de confirmación`
5. `El usuario recibe email de confirmación`
6. `El usuario hace clic en confirmar`
7. `El sistema activa la cuenta`
8. `El sistema envía bienvenida al usuario`

**Historia B (Email inválido):**
1. `El usuario completa el formulario de registro`
2. `El usuario ingresa un email inválido`
3. `El sistema valida el email`
4. `El sistema detecta email inválido`
5. `El sistema muestra mensaje de error`
6. `El sistema solicita email válido`

**Historia C (No confirmación):**
1. `El usuario completa el registro`
2. `El sistema envía email de confirmación`
3. `El usuario NO hace clic en confirmar`
4. `El sistema espera 24 horas`
5. `El sistema elimina el registro`

**Historia D (Usuario corporativo):**
1. `El usuario indica que es corporativo`
2. `El sistema detecta usuario corporativo`
3. `El sistema asigna automáticamente permisos corporativos`
4. `El sistema activa la cuenta`
5. `El sistema envía bienvenida corporativa`

---

### Ejemplo 2: Proceso de Aprobación de Presupuesto

#### Narrativa Original (con condicionales)
```
"El cliente solicita presupuesto. El vendedor prepara propuesta. Si el cliente es premium, aplica 10% descuento. Si es estándar, precio normal. Si es nuevo, 5% descuento. Una vez preparado, el vendedor envía al cliente. Si el cliente aprueba, cerramos venta. Si pide modificaciones, las hacemos. Si no responde en 7 días, enviamos recordatorio."
```

#### Condicionales Identificados
1. "Si el cliente es premium..." → rama por tipo cliente
2. "Si es estándar..." → rama por tipo cliente
3. "Si es nuevo..." → rama por tipo cliente
4. "Si el cliente aprueba..." → rama de decisión
5. "Si pide modificaciones..." → rama de cambio
6. "Si no responde en 7 días..." → rama de seguimiento

#### Historias Separadas (Sin Condicionales)

**Historia A (Cliente premium - Happy Path):**
1. `El cliente solicita presupuesto`
2. `El vendedor identifica que es cliente premium`
3. `El vendedor prepara la propuesta`
4. `El vendedor aplica 10% descuento por ser premium`
5. `El vendedor envía presupuesto al cliente`
6. `El cliente recibe el presupuesto`
7. `El cliente aprueba el presupuesto`
8. `El vendedor cierra la venta`

**Historia B (Cliente estándar):**
1. `El cliente solicita presupuesto`
2. `El vendedor identifica que es cliente estándar`
3. `El vendedor prepara la propuesta`
4. `El vendedor aplica precio normal (sin descuento)`
5. `El vendedor envía presupuesto al cliente`
6. `El cliente recibe el presupuesto`
7. `El cliente aprueba el presupuesto`
8. `El vendedor cierra la venta`

**Historia C (Cliente nuevo):**
1. `El cliente solicita presupuesto`
2. `El vendedor identifica que es cliente nuevo`
3. `El vendedor prepara la propuesta`
4. `El vendedor aplica 5% descuento por ser nuevo`
5. `El vendedor envía presupuesto al cliente`
6. `El cliente recibe el presupuesto`
7. `El cliente aprueba el presupuesto`
8. `El vendedor cierra la venta`

**Historia D (Modificaciones):**
1. `El cliente solicita presupuesto`
2. `El vendedor prepara propuesta`
3. `El vendedor envía presupuesto`
4. `El cliente recibe presupuesto`
5. `El cliente solicita modificaciones`
6. `El vendedor incorpora las modificaciones`
7. `El vendedor envía presupuesto revisado`
8. `El cliente aprueba presupuesto revisado`
9. `El vendedor cierra la venta`

**Historia E (Recordatorio):**
1. `El cliente solicita presupuesto`
2. `El vendedor prepara propuesta`
3. `El vendedor envía presupuesto`
4. `El cliente recibe presupuesto`
5. `El cliente NO responde`
6. `El sistema espera 7 días`
7. `El sistema envía recordatorio al cliente`

---

### Ejemplo 3: Proceso de Gestión de Inventario

#### Narrativa Original (con condicionales)
```
"Cuando llega material, el almacén lo recibe. Si coincide con la orden, se acepta. Si no, se rechaza y devuelve. Si el material está en buen estado, se almacena. Si está dañado, va a devoluciones. Si el stock después del ingreso supera el máximo, se devuelve exceso. Si está por debajo del mínimo, se genera orden de compra."
```

#### Condicionales Identificados
1. "Si coincide con la orden..." → rama de validación
2. "Si no..." → rama de rechazo
3. "Si el material está en buen estado..." → rama de calidad
4. "Si está dañado..." → rama de daño
5. "Si el stock supera el máximo..." → rama de exceso
6. "Si está por debajo del mínimo..." → rama de falta

#### Historias Separadas (Sin Condicionales)

**Historia A (Material correcto y en buen estado - Happy Path):**
1. `Llega material al almacén`
2. `El almacén verifica que coincide con la orden`
3. `El material coincide con la orden`
4. `El almacén verifica el estado del material`
5. `El material está en buen estado`
6. `El almacén acepta el material`
7. `El almacén almacena el material`

**Historia B (Material no coincide con orden):**
1. `Llega material al almacén`
2. `El almacén verifica que coincide con la orden`
3. `El material NO coincide con la orden`
4. `El almacén rechaza el material`
5. `El almacén devuelve el material`

**Historia C (Material dañado):**
1. `Llega material al almacén`
2. `El almacén verifica que coincide con la orden`
3. `El material coincide con la orden`
4. `El almacén verifica el estado del material`
5. `El material está dañado`
6. `El almacén envía material a devoluciones`

**Historia D (Exceso de stock):**
1. `Llega material al almacén`
2. `El almacén acepta el material`
3. `El almacén almacena el material`
4. `El sistema calcula el nuevo stock`
5. `El stock supera el máximo permitido`
6. `El sistema identifica exceso de stock`
7. `El almacén devuelve el exceso`

**Historia E (Orden de compra automática):**
1. `Se consume material del almacén`
2. `El sistema calcula el stock restante`
3. `El stock está por debajo del mínimo`
4. `El sistema genera orden de compra automáticamente`
5. `El responsable de compras recibe la orden`

---

## Resumen: Reglas para Eliminar Condicionales

### Reglas de Oro

1. **Una historia = un camino**
   - No mezclar múltiples rutas
   - Cada variación = historia separada

2. **Linearidad estricta**
   - Sin ramificaciones
   - Sin "si" en la narrativa principal

3. **Captura el 80% primero**
   - Happy path antes que excepciones
   - Variaciones después

4. **Estados como objetos**
   - Modela estados, no condiciones
   - Transiciones como pasos

5. **Eventos como disparadores**
   - Tiempo → eventos
   - No "si después de X tiempo"

### Señales de Alerta

❌ **"Si..."** → Dividir en historias
❌ **"Dependiendo de..."** → Separar casos
❌ **"A veces..."** → Capturar primero lo común
❌ **"Puede ser que..."** → Identificar probabilidad
❌ **"O bien... o bien..."** → Dos historias separadas

### Frases de Redirección

✅ **"Hablemos del caso más común"**
✅ **"¿Qué pasa normalmente?"**
✅ **"¿En el caso ideal?"**
✅ **"Sigamos el 80% primero"**
✅ **"Eso va en historia separada"**

**Recuerda:** El objetivo es crear historias simples, lineales y fáciles de entender, modelar e implementar. La simplicidad es más valiosa que la completitud inicial.
