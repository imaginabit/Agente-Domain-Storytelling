# Knowledge Crunching (Extracción de Conocimiento)

Este documento contiene metodologías avanzadas para extraer conocimiento tácito, asunciones implícitas, reglas no escritas y expertise oculto del experto del dominio, revelando la sabiduría práctica que no aparece en documentos formales.

## ¿Qué es Knowledge Crunching?

**Knowledge Crunching** es el proceso de **extraer conocimiento tácito** (lo que saben pero no dicen) del experto del dominio y transformarlo en conocimiento explícito (documentado, estructurado, transferible).

### Conocimiento Tácito vs. Explícito

| Conocimiento Tácito | Conocimiento Explícito |
|---------------------|------------------------|
| 🎓 "Lo sabemos por experiencia" | 📝 "Está en el manual" |
| 💡 "Es obvio para nosotros" | 📋 "Son las reglas oficiales" |
| 🤝 "Así se ha hecho siempre" | 📚 "Es la política documentada" |
| 👁️ "Lo vemos al instante" | 📊 "Está en los reportes" |
| 🧠 "Está en nuestra cabeza" | 💾 "Está en el sistema" |

### Características del Conocimiento Tácito
- ⚡ **Rápido acceso** - Se aplica instantáneamente
- 🎯 **Contextual** - Depende de la situación específica
- 👥 **Personal** - Reside en personas específicas
- 🔄 **Difícil de transferir** - "Se aprende con experiencia"
- 💎 **Valioso** - Años de experiencia condensados

---

## Tipos de Conocimiento Tácito

### 1. Reglas No Escritas

**Definición:** Políticas y criterios que se aplican pero no están documentados

**Ejemplos:**
- "Los clientes VIP siempre tienen prioridad"
- "Si el supervisor está de mal humor, mejor no pedir aprobaciones"
- "En diciembre nunca aprobamos gastos extras"
- "Las órdenes de [cliente X] siempre van al técnico Y"

**Cómo identificar:**
- "¿Hay alguna regla que no está en el manual?"
- "¿Cómo decide [actor] en casos borderline?"
- "¿Qué pasa cuando [condición]?"

**Ejemplo de extracción:**
```
Usuario: "Y entonces el supervisor aprueba la solicitud"
Tú: "¿Siempre la aprueba o hay casos donde la rechaza?"
Usuario: "Bueno, normalmente sí, pero si es viernes por la tarde..."
Tú: "¿Qué pasa si es viernes por la tarde?"
Usuario: "Ah, entonces dice que lo vea el lunes, no quiere aprobar antes del fin de semana"

CONOCIMIENTO TÁCITO EXTRAÍDO:
A1: Regla no escrita - No aprobar solicitudes los viernes tarde
Criterio: Solicitudes de vacaciones viernes PM
Razón: Evitar cambios de último minuto
Impacto: Retrasa 3 días solicitudes viernes
```

---

### 2. Criterios de Decisión Implícitos

**Definición:** Factores que influyen en decisiones pero no están formalizados

**Ejemplos:**
- "Este cliente es de alto valor, le damos trato especial"
- "Si es urgente, pero no es VIP, escalamos al responsable"
- "Con [años experiencia], sabemos que esto va a funcionar"

**Cómo identificar:**
- "¿Qué factores considera para decidir [X]?"
- "¿Cómo weighing diferentes criterios?"
- "¿Hay alguna ponderación especial?"

**Ejemplo de extracción:**
```
Usuario: "El buyer compara las cotizaciones y elige la mejor"
Tú: "¿Qué significa 'mejor'?"
Usuario: "Pues precio, calidad, plazos... ya sabe"
Tú: "¿Cómo weighing cada factor?"
Usuario: "Precio es 40%, calidad 35%, plazos 25%"
Tú: "¿Eso está documentado?"
Usuario: "No, es lo que hemos aprendido con experiencia"

CONOCIMIENTO TÁCITO EXTRAÍDO:
C1: Criterios de selección de proveedores
Peso: Precio 40%, Calidad 35%, Plazos 25%
Aplicable: Todas las compras >€1000
Excepciones: Emergencia (plazos 50%)
```

---

### 3. Conocimiento de Excepciones

**Definición:** Casos especiales que "rompen las reglas" pero son importantes

**Ejemplos:**
- "Normalmente no hacemos X, pero para [cliente/especial] sí"
- "La regla dice A, pero en este caso específico hacemos B"
- "Hay una excepción no oficial para [situación]"

**Cómo identificar:**
- "¿Hay casos donde no siguen la regla?"
- "¿Qué excepciones importantes existen?"
- "¿Cuándo hacen algo diferente?"

**Ejemplo de extracción:**
```
Usuario: "Y entonces RRHH registra al empleado en el sistema"
Tú: "¿Siempre hacen esto inmediatamente?"
Usuario: "Sí, normalmente"
Tú: "¿Hay casos donde no?"
Usuario: "Bueno, si es alta temporal, a veces esperamos una semana"
Tú: "¿Por qué?"
Usuario: "Porque las temporales a veces no duran, evitamos paperwork"

CONOCIMIENTO TÁCITO EXTRAÍDO:
E1: Excepción - Empleados temporales
Condición: Contratos <3 meses
Desvío: Esperar 1 semana antes de registrar
Razón: Evitar alta/baja administrativa si no dura
```

---

### 4. Workarounds y Soluciones Temporales

**Definición:** "Trucos" y soluciones no oficiales que se han desarrollado

**Ejemplos:**
- "Para que funcione, primero tienes que hacer X"
- "Nuestro truco es hacer Y antes de Z"
- "Si no funciona, hazlo así..."

**Cómo identificar:**
- "¿Hay algún 'truco' para que esto funcione mejor?"
- "¿Cómo han aprendido a hacerlo más rápido?"
- "¿Qué hacen cuando el proceso normal no funciona?"

**Ejemplo de extracción:**
```
Usuario: "El sistema a veces se cuelga al generar facturas"
Tú: "¿Cómo lo resuelven?"
Usuario: "Ah, si se cuelga, cierras el sistema, esperas 5 minutos y vuelves a entrar"
Tú: "¿Eso está en el manual?"
Usuario: "No, es lo que hemos aprendido"

CONOCIMIENTO TÁCITO EXTRAÍDO:
W1: Workaround - Sistema colgado
Síntoma: Sistema no responde al generar factura
Solución: Cerrar sistema + esperar 5 min + reiniciar
Tasa éxito: 90%
Documentación: No oficial
```

---

### 5. Dependencias Ocultas

**Definición:** Relaciones y dependencias que no son obvias

**Ejemplos:**
- "Esto depende de que X haya terminado antes"
- "Si Y no está disponible, esto no funciona"
- "Necesitamos que [persona X] esté involucrada"

**Cómo identificar:**
- "¿De qué depende que esto funcione?"
- "¿Qué tiene que estar disponible?"
- "¿Quién más está involucrado?"

**Ejemplo de extracción:**
```
Usuario: "El técnico hace el trabajo y genera el parte"
Tú: "¿Puede hacer el parte inmediatamente?"
Usuario: "No, tiene que volver a la oficina"
Tú: "¿Por qué no lo hace en el lugar?"
Usuario: "Porque necesita acceso al sistema y en muchos sitios no hay buena conexión"
Tú: "¿Y eso siempre es un problema?"
Usuario: "Sí, en unos 30% de trabajos"

CONOCIMIENTO TÁCITO EXTRAÍDO:
D1: Dependencia - Acceso a sistema
Requisito: Conexión estable a red corporativa
Disponibilidad: 70% de ubicaciones
Impacto: 30% requiere retorno a oficina
Alternativa: Almacenamiento offline (no implementado)
```

---

### 6. Patrones y Tendencias

**Definición:** Patrones que se han observado empíricamente

**Ejemplos:**
- "Los clientes de [tipo X] siempre piden descuentos"
- "En [mes/temporada] siempre hay más trabajo"
- "[Tipo orden] normalmente toma más tiempo"

**Cómo identificar:**
- "¿Han notado algún patrón?"
- "¿Hay tendencias que pueden predecir?"
- "¿Qué diferencias hay entre tipos de [objeto]?"

**Ejemplo de extracción:**
```
Usuario: "Y entonces el cliente paga la factura"
Tú: "¿Suelen pagar a tiempo?"
Usuario: "Depende, normalmente sí"
Tú: "¿Hay tipos de clientes que paguen más lento?"
Usuario: "Sí, los constructores siempre pagan tarde, es típico del sector"
Tú: "¿Cuánto más tarde normalmente?"
Usuario: 2-3 semanas más que otros

CONOCIMIENTO TÁCITO EXTRAÍDO:
P1: Patrón - Sector construcción
Tipo cliente: Empresas de construcción
Comportamiento pago: +2-3 semanas vs promedio
Frecuencia: 90% de clientes construcción
Predictibilidad: Alta
```

---

## Técnicas de Knowledge Crunching

### 1. Técnica del "¿Por Qué?" (5 Whys)

**Objetivo:** Llegar a la causa raíz del conocimiento tácito

**Proceso:**
1. Pregunta "¿por qué?" sobre una afirmación
2. Toma la respuesta y pregunta "¿por qué?" otra vez
3. Repite hasta llegar a la causa raíz
4. Documenta cada nivel de "¿por qué?"

**Ejemplo completo:**
```
Afirmación: "No enviamos órdenes los viernes por la tarde"

Tú: "¿Por qué no envían órdenes los viernes por la tarde?"
Usuario: "Porque los proveedores no las procesan hasta el lunes"
Tú: "¿Por qué no las procesan hasta el lunes?"
Usuario: "Porque su sistema se actualiza el sábado por la mañana"
Tú: "¿Por qué se actualiza el sábado por la mañana?"
Usuario: "Porque es el único día que pueden parar sin afectar operaciones"
Tú: "¿Por qué no pueden parar otro día?"
Usuario: "Porque tienen órdenes pendientes que deben cumplir"

CAUSA RAÍZ: Dependencia de sistema proveedor que se actualiza sábado
POLÍTICA TÁCITA: No enviar órdenes viernes PM para evitar procesamiento diferido
CONOCIMIENTO: Proveedor [X] requiere 48h lead time para actualizaciones
```

### 2. Técnica de Profundización por Contraste

**Objetivo:** Revelar diferencias que destacan reglas implícitas

**Proceso:**
1. Identifica un caso "normal"
2. Contrasta con caso "diferente"
3. Pregunta qué hace diferentes a los casos
4. Extrae criterios implícitos

**Ejemplo completo:**
```
Caso A (Normal): Cliente standard solicita servicio
Flujo: Solicitud → Evaluación → Aprobación → Asignación técnico

Caso B (Diferente): Cliente VIP solicita servicio
Flujo: Solicitud → Aprobación automática → Asignación técnico top

Tú: "¿Qué hace que sea VIP?"
Usuario: "Volumen de compra >€100k/año"
Tú: "¿Hay otros criterios?"
Usuario: "También si es estratégico, aunque compre menos"

CRITERIOS TÁCITOS EXTRAÍDOS:
Criterio 1: Volumen anual >€100k (objetivo)
Criterio 2: Cliente estratégico (subjetivo)
Beneficio VIP: Skip evaluación manual
Beneficio VIP: Técnicos senior asignados
```

### 3. Técnica de Escenarios Extremos

**Objetivo:** Descubrir límites y excepciones al explorar casos raros

**Proceso:**
1. Toma un proceso normal
2. Explora casos extremos ("¿Y si X?")
3. Descubre excepciones y reglas especiales
4. Identifica workarounds para casos especiales

**Ejemplo completo:**
```
Proceso normal: Cliente solicita servicio → Asignación técnico

Tú: "¿Qué pasa si el cliente es urgente pero es viernes tarde?"
Usuario: "Ah, entonces es complicado"
Tú: "¿Por qué?"
Usuario: "Porque el supervisor no quiere aprobar nada"
Tú: "¿Y cómo resuelven urgencias entonces?"
Usuario: "El técnico de guardia puede ir, pero necesita aprobación del director"
Tú: "¿Y el director está disponible?"
Usuario: "No siempre, entonces a veces el técnico va sin aprobación formal"

CONOCIMIENTO TÁCITO EXTRAÍDO:
Escenario: Urgencia + viernes tarde + director no disponible
Desvío: Técnico de guardia puede proceder sin aprobación
Riesgo: Asume responsabilidad personal
Workaround: Aprobación retroactiva al día siguiente
```

### 4. Técnica de Mining de Workarounds

**Objetivo:** Revelar soluciones temporales que indican problemas

**Proceso:**
1. Pregunta "¿Qué hacen cuando no funciona normal?"
2. Profundiza en el workaround
3. Pregunta "¿Por qué no funciona normal?"
4. Identifica problema subyacente

**Ejemplo completo:**
```
Tú: "¿Qué hacen cuando el sistema está lento?"
Usuario: "Usamos una hoja de cálculo en paralelo"
Tú: "¿Con qué frecuencia pasa esto?"
Usuario: "Unas 3 veces por semana"
Tú: "¿Por qué está lento el sistema?"
Usuario: "Es muy antiguo, no aguanta el volumen"
Tú: "¿Y la hoja de cálculo funciona mejor?"
Usuario: "Para algunas cosas sí, para otras no"

CONOCIMIENTO TÁCITO EXTRAÍDO:
Problema: Sistema legacy no escala
Workaround: Hoja de cálculo paralela
Cobertura: 60% de funciones críticas
Riesgo: Datos inconsistentes entre sistema y Excel
Percepción usuario: Excel más confiable que sistema oficial
```

### 5. Técnica de Identificación de Asunciones

**Objetivo:** Revelar lo que "todos saben" pero nadie dice

**Proceso:**
1. Identifica afirmaciones con "siempre", "normalmente", "obviamente"
2. Pregunta "¿Y si no fuera así?"
3. Revela la asunción implícita
4. Documenta dependencia

**Ejemplo completo:**
```
Afirmación: "El sistema siempre calcula los descuentos correctamente"
Tú: "¿Y si no calculara correctamente?"
Usuario: "No, siempre está bien"
Tú: "¿Cómo lo saben?"
Usuario: "Porque hemos trabajado así siempre"
Tú: "¿Han verificado alguna vez?"
Usuario: "Bueno, no realmente, confiamos en que funciona"

ASUNCIÓN IMPLÍCITA:
A1: Cálculo de descuentos es correcto
Evidencia: Ninguna verificación explícita
Razón: "Siempre ha funcionado"
Riesgo: Error no detectado en descuentos
Recomendación: Auditoría de cálculos
```

### 6. Técnica de Extracción de Factores Ocultos

**Objetivo:** Identificar variables que influyen en decisiones pero no se mencionan

**Proceso:**
1. Observa decisiones aparentemente simples
2. Pregunta "¿Qué factores considera?"
3. Identifica factores no obvios
4. Revela ponderaciones implícitas

**Ejemplo completo:**
```
Decisión: Asignación de técnico a orden

Tú: "¿Cómo asignan técnicos?"
Usuario: "Según disponibilidad y experiencia"
Tú: "¿Qué otros factores consideran?"
Usuario: "Ubicación, creo"
Tú: "¿Y la carga de trabajo actual?"
Usuario: "Ah sí, también"
Tú: "¿Cómo weight cada factor?"
Usuario: "Disponibilidad 40%, experiencia 30%, ubicación 20%, carga 10%"

FACTORES TÁCITOS EXTRAÍDOS:
Factor 1: Disponibilidad (40%)
Factor 2: Experiencia en tipo trabajo (30%)
Factor 3: Proximidad geográfica (20%)
Factor 4: Carga actual de trabajo (10%)
Cálculo: Score ponderado = (disp×0.4) + (exp×0.3) + (prog×0.2) + (carga×0.1)
```

---

## Ejemplos Completos de Knowledge Crunching

### Ejemplo 1: Proceso de Aprobación de Gastos

#### Narrativa Original
"El empleado envía solicitud de gasto. El supervisor aprueba. Se paga el gasto."

#### Knowledge Crunching Session

**Tú:** "Cuéntame cómo funciona una solicitud de gasto típica"
**Usuario:** "El empleado envía la solicitud con facturas y justificación"
**Tú:** "¿Y el supervisor siempre aprueba?"
**Usuario:** "Normalmente sí"
**Tú:** "¿En qué casos NO aprobaría?"
**Usuario:** "Bueno, si es muy caro o no está justificado"
**Tú:** "¿Qué considera 'muy caro'?"
**Usuario:** "Eso depende..."
**Tú:** "¿Depende de qué?"
**Usuario:** "Del empleado, del tipo de gasto... es complicado"

**Profundización:**
**Tú:** "¿Puede darme un ejemplo de algo que aprobaría y algo que no?"
**Usuario:** "Sí, si un empleado junior pide €500 para formación, lo apruebo. Pero si pide €200 para cena con cliente, no."
**Tú:** "¿Por qué la diferencia?"
**Usuario:** "La formación es una inversión, la cena con cliente no está clara"
**Tú:** "¿Hay reglas para cenas con clientes?"
**Usuario:** "Sí, tienen que ser con clientes potenciales y máximo €50"

**Extrayendo más:**
**Tú:** "¿Y qué pasa con empleados senior?"
**Usuario:** "Ah, ellos tienen más libertad, pueden gastar más"
**Tú:** "¿Cuánto más?"
**Usuario:** "Un senior puede pedir hasta €300 para cena"

**Descubriendo excepciones:**
**Tú:** "¿Hay casos especiales?"
**Usuario:** "Sí, si es un cliente muy importante, pueden pedir lo que sea"
**Tú:** "¿Cómo saben si es 'muy importante'?"
**Usuario:** "Es obvio, clientes estratégicos, los de más volumen"

#### Conocimiento Tácito Extraído

```
REGLAS NO ESCRITAS:

R1: Criterios por nivel de empleado
- Junior: Formación OK (<€500), cenas NO
- Senior: Formación OK, cenas OK (<€300)
- Director: Sin límite para clientes estratégicos

R2: Criterios por tipo de gasto
- Formación: Inversión, aprobada si relevante
- Cenas con clientes: Sospechosas, requieren justificación adicional
- Cenas con clientes estratégicos: Sin límite

R3: Clientes estratégicos
- Criterio: Volumen de compra o potencial estratégico
- Definición: Implícita, basada en historial
- Aprobación: Automática para gastos relacionados

PATRONES:
P1: Gastos de formación más aceptados que gastos sociales
P2: Empleados senior tienen más discreción
P3: Clientes grandes = reglas diferentes

ASUNCIONES:
A1: Empleados senior toman mejores decisiones
A2: Clientes estratégicos justifican cualquier gasto
A3: Formación siempre es buena inversión
```

---

### Ejemplo 2: Proceso de Selección de Proveedores

#### Narrativa Original
"Buscamos proveedores, pedimos cotizaciones, elegimos la mejor y compramos."

#### Knowledge Crunching Session

**Tú:** "Cuéntame cómo eligen un proveedor"
**Usuario:** "Buscamos en nuestro catálogo de proveedores, pedimos cotización, comparamos y elegimos"
**Tú:** "¿Qué catalog usan?"
**Usuario:** "Tenemos una lista de proveedores aprobados"
**Tú:** "¿Cómo se aprueba un proveedor?"
**Usuario:** "Bueno, si han trabajado bien antes"
**Tú:** "¿Y si no han trabajado antes?"
**Usuario:** "Entonces hay que evaluarlos"

**Profundizando:**
**Tú:** "¿Cómo evalúan proveedores nuevos?"
**Usuario:** "Vemos su experiencia, referencias, certificaciones..."
**Tú:** "¿Todas las certificaciones pesan igual?"
**Usuario:** "No, algunas son más importantes"
**Tú:** "¿Cuáles son más importantes?"
**Usuario:** "ISO 9001 es crítica, las otras menos"

**Descubriendo criterios ocultos:**
**Tú:** "¿El precio es el factor principal?"
**Usuario:** "No, es importante pero no todo"
**Tú:** "¿Qué más es importante?"
**Usuario:** "Calidad, plazos, ubicación..."
**Tú:** "¿Cómo weight cada factor?"
**Usuario:** "Depende del tipo de compra"
**Tú:** "¿Puede dar ejemplos?"

**Ejemplos específicos:**
**Usuario:** "Para suministros estándar, precio es 60%, calidad 25%, plazos 15%"
**Tú:** "¿Y para servicios especializados?"
**Usuario:** "Ah, entonces es diferente, calidad 50%, experiencia 30%, precio 20%"
**Tú:** "¿Y la ubicación?"
**Usuario:** "Eso es más para urgencia, si es urgente preferimos cercanos"

#### Conocimiento Tácito Extraído

```
CRITERIOS POR TIPO DE COMPRA:

Tipo 1: Suministros estándar
- Precio: 60%
- Calidad: 25%
- Plazos: 15%
Ubicación: Solo para urgencia

Tipo 2: Servicios especializados
- Calidad: 50%
- Experiencia: 30%
- Precio: 20%
Ubicación: Irrelevante

CATEGORIZACIÓN TÁCITA:
Categoría A: Proveedores preferidos
- Historial >3 años
- Sin incidentes
- Certificación ISO 9001
- Evaluación automática

Categoría B: Proveedores nuevos
- Evaluación manual completa
- Certificaciones requeridas
- Período de prueba
- Límites de compra iniciales

FACTORES DECISIVOS:
Factor 1: Certificaciones (ISO 9001 crítica)
Factor 2: Historial (3+ años sin incidentes)
Factor 3: Tipo de compra (define criterios)
Factor 4: Urgencia (cambia peso de ubicación)

EXCEPCIONES:
E1: Cliente específico prefiere proveedor X
E2: Emergencia = ubicación > calidad
E3: Proveedor existente = skip evaluación inicial
```

---

### Ejemplo 3: Proceso de Control de Calidad

#### Narrativa Original
"El inspector revisa el producto. Si cumple estándares, aprueba. Si no, rechaza."

#### Knowledge Crunching Session

**Tú:** "Cuéntame cómo funciona el control de calidad"
**Usuario:** "Cada producto pasa por inspección"
**Tú:** "¿Qué inspecciona?"
**Usuario:** "Los criterios de calidad"
**Tú:** "¿Cuáles son?"
**Usuario:** "Dimensiones, funcionalidad, apariencia..."
**Tú:** "¿Todos pesan igual?"
**Usuario:** "No, depende del producto"
**Tú:** "¿Puede dar un ejemplo?"

**Profundizando:**
**Usuario:** "Para una pieza mecánica, dimensiones son 50%, funcionalidad 40%, apariencia 10%"
**Tú:** "¿Y para un producto estético?"
**Usuario:** "Ah, entonces es diferente, apariencia 60%, funcionalidad 30%, dimensiones 10%"
**Tú:** "¿Cómo decide la importancia?"
**Usuario:** "Es según el uso final del producto"
**Tú:** "¿Quién define eso?"
**Usuario:** "Ingeniería nos dice"

**Descubriendo subjetividad:**
**Tú:** "¿La apariencia es objetiva o subjetiva?"
**Usuario:** "Hay elementos objetivos y subjetivos"
**Tú:** "¿Cuáles son objetivos?"
**Usuario:** "Color uniforme, sin rayones, acabados correctos"
**Tú:** "¿Y subjetivos?"
**Usuario:** "Si se ve 'bien' o 'profesional', es subjetivo"
**Tú:** "¿Cómo maneja la subjetividad?"
**Usuario:** "El inspector senior decide"

#### Conocimiento Tácito Extraído

```
CRITERIOS POR TIPO DE PRODUCTO:

Tipo 1: Piezas mecánicas
- Dimensiones: 50% (objetivo)
- Funcionalidad: 40% (objetivo)
- Apariencia: 10% (mixto)

Tipo 2: Productos estéticos
- Apariencia: 60% (60% subjetivo, 40% objetivo)
- Funcionalidad: 30% (objetivo)
- Dimensiones: 10% (objetivo)

ELEMENTOS OBJETIVOS:
- Mediciones (dimensiones)
- Pruebas funcionales
- Especificaciones técnicas

ELEMENTOS SUBJETIVOS:
- Apariencia "profesional"
- Acabado "de calidad"
- Presentación "correcta"

REGLAS DE DECISIÓN:
R1: Inspector junior → Solo elementos objetivos
R2: Inspector senior → Puede decidir elementos subjetivos
R3: Elementos objetivos + subjetivos → Revisión por supervisor

ASUNCIONES:
A1: Inspector senior tiene mejor criterio visual
A2: Elementos subjetivos = experiencia + intuición
A3: Cliente percibirá calidad como inspector

CONOCIMIENTO TÁCITO:
- No todos los inspectores pueden evaluar subjetivo
- La "calidad visual" es real pero no cuantificable
- Mismo producto, criterios diferentes según uso final
- Dependencia de expertise del inspector
```

---

## Errores Comunes en Knowledge Crunching

### Error 1: No Profundizar Suficiente

❌ **Problema:**
```
Usuario: "Comparamos las cotizaciones"
Tú: "¿Y eligen la mejor?"
❌ (no profundizar)

Tú: "¿Cómo comparan? ¿Qué factores consideran?"
✅ (profundizar)
```

### Error 2: Aceptar "Obviamente" Sin Explorar

❌ **Problema:**
```
Usuario: "Es obvio que esto es mejor"
Tú: "Entiendo"
❌ (asumir conocimiento común)

Tú: "¿Qué lo hace obvio? ¿Qué criterios usan?"
✅ (extraer criterios)
```

### Error 3: No Validar Conocimiento Tácito

❌ **Problema:**
```
Usuario: "Normalmente funciona así"
Tú: "Perfecto, lo documento"
❌ (no validar)

Tú: "¿Eso es siempre cierto o hay excepciones?"
✅ (descubrir excepciones)
```

### Error 4: Mezclar Conocimiento con Opiniones

❌ **Problema:**
```
Usuario: "Creo que esto es mejor"
Tú: "Lo marco como regla"
❌ (confundir opinión con práctica)

Tú: "¿Es su opinión o es lo que hace la empresa?"
✅ (separar opinión de política)
```

### Error 5: No Identificar Dependencias

❌ **Problema:**
```
Usuario: "Esto funciona así"
Tú: "Lo documento"
❌ (no explorar dependencias)

Tú: "¿De qué depende que funcione así?"
✅ (descubrir dependencias ocultas)
```

---

## Resumen: Knowledge Crunching

### Principios Clave

1. **No hay conocimiento común** - Todo debe extraerse
2. **Pregunta "¿por qué?"** - Hasta llegar a causa raíz
3. **Contraste casos** - Normal vs. diferente revela reglas
4. **Explora excepciones** - Los casos especiales iluminan reglas
5. **Identifica asunciones** - "Obvio" = conocimiento tácito

### Técnicas de Extracción

- **5 Whys** - Causa raíz
- **Contraste** - Normal vs. especial
- **Escenarios extremos** - Límites y excepciones
- **Mining workarounds** - Problemas subyacentes
- **Identificar asunciones** - "Siempre" y "obviamente"
- **Factores ocultos** - Variables no obvias

### Conocimiento a Extraer

- 🎯 **Reglas no escritas** - Políticas no documentadas
- 📊 **Criterios implícitos** - Factores de decisión
- ⚠️ **Excepciones** - Casos que rompen reglas
- 🔧 **Workarounds** - Soluciones temporales
- 🔗 **Dependencias** - Relaciones ocultas
- 📈 **Patrones** - Tendencias observadas

**Recuerda:** El conocimiento tácito es el verdadero valor del experto. Tu trabajo es extraerlo, documentarlo y hacerlo accesible. Lo que es "obvio" para ellos es oro para el resto. Profundiza siempre, nunca asumas.
