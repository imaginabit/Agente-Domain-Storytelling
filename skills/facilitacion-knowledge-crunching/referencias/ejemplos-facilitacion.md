# Ejemplos de Facilitación Completa

Este documento contiene sesiones completas de facilitación que muestran cómo aplicar todas las técnicas de knowledge crunching, detección de plot holes, identificación de pain points y uso de anotaciones en sesiones reales de Domain Storytelling.

## Sesión 1: Proceso de Facturación

### Contexto
**Objetivo:** Modelar proceso de facturación desde orden completada hasta cobro
**Participantes:**
- Facilitador (tú)
- Experto del dominio: Responsable administrativo (María)

### Inicio de la Sesión

**Facilitador:** "María, gracias por acompañarnos. Hoy queremos entender cómo funciona el proceso de facturación desde que una orden se completa hasta que recibimos el pago. Cuéntame tu historia paso a paso, empezando por el principio."

**María:** "Bueno, cuando el técnico termina una orden, genera el parte de trabajo en su tablet."

**Facilitador:** *(anotando)* "Perfecto. ¿Qué pasa después?"

**María:** "Luego el sistema calcula automáticamente los costes y genera la factura."

**Facilitador:** *(detectando plot hole)* "Un momento, ¿cómo va exactamente del parte de trabajo a la factura? ¿El técnico hace algo más?"

**María:** "Ah sí, sube el parte al sistema desde el tablet."

**Facilitador:** "Entiendo. ¿Y entonces el sistema calcula los costes?"

**María:** "Sí, coge las horas trabajadas, materiales, desplazamiento..."

**Facilitador:** "Perfecto. ¿Y después?"

**María:** "Después yo reviso la factura y se la envío al cliente."

---

### Profundización (Knowledge Crunching)

**Facilitador:** "María, cuando revisas la factura, ¿en qué te fijas?"

**María:** "Bueno, que los datos del cliente estén bien, que los importes sean correctos..."

**Facilitador:** "¿Los importes siempre son correctos?"

**María:** "Normalmente sí, pero a veces hay que ajustar algo."

**Facilitador:** *(detectando pain point)* "¿Con qué frecuencia pasa eso?"

**María:** "Unas 3 de cada 10 facturas, tengo que cambiar algo."

**Facilitador:** *(anotando P1)* "¿Y qué sueles cambiar?"

**María:** "Los materiales principalmente, a veces el técnico mete mal una cantidad."

**Facilitador:** "Y cuando envías la factura al cliente, ¿cómo lo haces?"

**María:** "Por email, le mando el PDF."

**Facilitador:** "¿Siempre funciona bien?"

**María:** "Casi siempre, pero a veces el email va a spam."

**Facilitador:** "¿Y cómo sabes si llegó?"

**María:** "Si no me dicen nada en 3 días, asumo que llegó."

**Facilitador:** *(detectando gap)* "¿Y si no responde?"

**María:** "Entonces esperamos 15 días y enviamos recordatorio."

---

### Identificación de Pain Points

**Facilitador:** "María, has mencionado varias cosas. Me gustaría entender mejor los problemas. Cuando dices que a veces hay que ajustar materiales, ¿qué pasa exactamente?"

**María:** "Es que el técnico escribe en el tablet, y a veces se equivoca con las cantidades."

**Facilitador:** "¿Con qué frecuencia se equivoca?"

**María:** "Unas 3 de cada 10 órdenes, como te dije."

**Facilitador:** "Eso es bastante. ¿Y cuánto tiempo te toma corregirlo?"

**María:** "Depende, pero entre 10 y 15 minutos por factura."

**Facilitador:** *(calculando impacto)* "¿Y cuántas facturas haces por mes?"

**María:** "Unas 100, más o menos."

**Facilitador:** *(anotando P1 con métricas)*
```
P1: Errores en transcripción materiales
Frecuencia: 30%
Tiempo perdido: 10-15 min/factura
Impacto: 30-45 horas/mes
Causa: Datos introducidos manualmente en tablet
```

---

### Detección de Conocimiento Tácito

**Facilitador:** "María, cuando revisas si los importes son correctos, ¿cómo sabes si están bien?"

**María:** "Bueno, veo si coinciden con el presupuesto."

**Facilitador:** "¿Siempre hay presupuesto previo?"

**María:** "Sí, para órdenes >€500 siempre hacemos presupuesto antes."

**Facilitador:** *(identificando regla no escrita)* "¿Y para órdenes menores a €500?"

**María:** "Ah, esas no necesitan presupuesto, van directo."

**Facilitador:** "¿Hay otras reglas para presupuestos?"

**María:** "También los clientes nuevos siempre requieren presupuesto, aunque sea poca cantidad."

**Facilitador:** *(extrayendo conocimiento tácito)*
```
REGLAS NO ESCRITAS:
R1: Órdenes >€500 → Presupuesto obligatorio
R2: Clientes nuevos → Presupuesto obligatorio
R3: Otros casos → Sin presupuesto
```

---

### Anotaciones en Tiempo Real

**Facilitador:** *(organizando anotaciones)*
```
ANOTACIONES - Proceso de Facturación

=== VARIACIONES (V) ===
V1: Cliente nuevo
Contexto: Paso 3 (revisar factura)
Frecuencia: 15%
Descripción: Clientes nuevos requieren presupuesto independientemente del importe
Prioridad: Media

=== PAIN POINTS (P) ===
P1: Errores transcripción materiales
Contexto: Paso 2 (calcular costes)
Frecuencia: 30%
Tiempo: 10-15 min/factura
Impacto: 30-45 horas/mes
Prioridad: Alta

P2: Emails a spam
Contexto: Paso 5 (enviar factura)
Frecuencia: 10%
Impacto: Demora en confirmación
Prioridad: Media

=== ASUNCIONES (A) ===
A1: Cliente confirma recepción
Contexto: Paso 6 (cliente recibe)
Asunción: Si no hay respuesta en 3 días, llegó correctamente
Riesgo: Email perdido sin saber
Prioridad: Alta

=== PREGUNTAS (Q) ===
Q1: Criterios validación importes
Contexto: Paso 3 (revisar factura)
Pregunta: ¿Qué proceso exacto usa para validar importes?
Estado: Pendiente
```

---

### Historia Principal Refinada

**Facilitador:** "María, vamos a recapitular la historia principal, el caso normal. ¿Empezamos de nuevo?"

**María:** "Claro. El técnico termina la orden en el tablet. Sube el parte al sistema. El sistema calcula costes automáticamente. Yo reviso la factura, corrijo si es necesario, y envío el PDF por email al cliente. El cliente confirma recepción o paga."

**Facilitador:** *(numerando)*
```
Historia Principal - Facturación (Happy Path)

1. `Técnico completa orden`
2. `Técnico genera parte de trabajo en tablet`
3. `Técnico sube parte al sistema`
4. `Sistema calcula costes automáticamente`
5. `Administrativo revisa factura`
6. `Administrativo corrige errores si necesario`
7. `Administrativo envía factura por email`
8. `Cliente recibe factura`
9. `Cliente confirma recepción`
10. `Cliente paga factura`
```

---

### Validación Final

**Facilitador:** "¿Esta historia refleja el proceso normal, el 80% de casos?"

**María:** "Sí, bastante."

**Facilitador:** "¿Falta algo importante?"

**María:** "Creo que está bien."

**Facilitador:** "Perfecto. Ahora, estas anotaciones que hemos registrado - ¿podemos hablar de algunas en detalle?"

**María:** "Claro."

---

## Sesión 2: Proceso de Contratación

### Contexto
**Objetivo:** Modelar proceso de contratación desde necesidad hasta incorporación
**Participantes:**
- Facilitador (tú)
- Experto del dominio: Responsable RRHH (Carlos)

### Inicio

**Facilitador:** "Carlos, queremos entender cómo contratamos nuevos empleados. Cuéntame desde el inicio hasta que la persona empieza a trabajar."

**Carlos:** "Cuando necesitamos personal, publicamos la oferta."

**Facilitador:** "¿Dónde la publican?"

**Carlos:** "En portales de empleo."

**Facilitador:** "¿Qué pasa después?"

**Carlos:** "Los candidatos envían currículums."

**Facilitador:** "¿Y entonces?"

**Carlos:** "El recruiter revisa los CVs y selecciona los mejores para entrevista."

**Facilitador:** *(detectando gap)* "¿Cómo reciben las aplicaciones? ¿El sistema las registra?"

**Carlos:** "Sí, las reciben por email y las metemos en una hoja de cálculo."

**Facilitador:** *(anotando workaround)* "¿Y después de seleccionar candidatos?"

**Carlos:** "Los convocamos a entrevista."

---

### Profundización - Knowledge Crunching

**Facilitador:** "Carlos, cuando el recruiter revisa CVs, ¿en qué se fija?"

**Carlos:** "En la experiencia, formación, referencias..."

**Facilitador:** "¿Todo pesa igual?"

**Carlos:** "No, la experiencia es lo más importante, 50%."

**Facilitador:** "¿Y los otros?"

**Carlos:** "Formación 30%, referencias 20%."

**Facilitador:** *(extrayendo criterios implícitos)* "¿Eso está documentado?"

**Carlos:** "No, es lo que hemos aprendido."

**Facilitador:** "¿Hay excepciones? ¿Tipos de puestos diferentes?"

**Carlos:** "Sí, para puestos técnicos la formación pesa más."

**Facilitador:** "¿Cuánto más?"

**Carlos:** "Formación 60%, experiencia 30%, referencias 10%."

**Facilitador:** *(documentando conocimiento tácito)*
```
CRITERIOS REVISIÓN CVs:

Tipo 1: Puestos comerciales/administrativos
- Experiencia: 50%
- Formación: 30%
- Referencias: 20%

Tipo 2: Puestos técnicos
- Formación: 60%
- Experiencia: 30%
- Referencias: 10%
```

---

### Identificación de Pain Points

**Facilitador:** "Carlos, cuando revisa CVs, ¿cuántos reciben normalmente?"

**Carlos:** "Depende, pero unos 50 por posición."

**Facilitador:** "¿Y cuántos revisa?"

**Carlos:** "Todos."

**Facilitador:** *(detectando pain point)* "¿Eso toma mucho tiempo?"

**Carlos:** "Sí, unas 3 horas."

**Facilitador:** "¿Y todos son relevantes?"

**Carlos:** "No, muchos no cumplen ni los requisitos mínimos."

**Facilitador:** "¿Por ejemplo?"

**Carlos:** "Piden nivel de inglés que no tienen, o experiencia que no coincide."

**Facilitador:** *(anotando pain point)*
```
P1: Revisión manual de CVs no calificados
Frecuencia: 100% posiciones
Tiempo perdido: 3 horas/posición
Causa: Sin filtro automático inicial
Impacto: RRHH saturado, tiempo mal utilizado
```

---

### Detección de Asunciones

**Facilitador:** "Carlos, cuando seleccionan candidatos para entrevista, ¿cómo saben que son los mejores?"

**Carlos:** "Según los criterios que te dije."

**Facilitador:** "¿Y si dos candidatos tienen puntaje similar?"

**Carlos:** "Entonces vemos referencias, o experiencia específica."

**Facilitador:** "¿Y si aún así están parejos?"

**Carlos:** "Aquí ya es más subjetivo, vemos 'fit' con el equipo."

**Facilitador:** *(detectando subjetividad)* "¿Eso está definido?"

**Carlos:** "No, es feeling."

**Facilitador:** *(documentando)*
```
ASUNCIONES:
A1: "Fit" con equipo es medible
A2: Referentes dan información confiable
A3: Scoring manual es objetivo
```

---

### Exploración de Workarounds

**Facilitador:** "Carlos, mencionaste que meten las aplicaciones en una hoja de cálculo. ¿Por qué no usan un sistema?"

**Carlos:** "Hemos probado varios, pero none funciona bien para lo que necesitamos."

**Facilitador:** "¿Qué les falta?"

**Carlos:** "Necesitamos algo simple, que filtre por palabras clave básicas."

**Facilitador:** "¿Y no existe eso?"

**Carlos:** "No hemos encontrado nada que se ajuste."

**Facilitador:** *(descubriendo necesidad)*
```
NECESIDAD IDENTIFICADA:
Sistema de filtering automático por:
- Palabras clave
- Años experiencia
- Formación
- Ubicación

ESTADO ACTUAL:
- Usando Excel como workaround
- 100% manual
- Ineficiente
```

---

### Anotaciones Organizadas

**Facilitador:** *(creando estructura)*
```
ANOTACIONES - Proceso de Contratación

=== VARIACIONES (V) ===
V1: Posición urgente
Contexto: Paso 1 (publicar oferta)
Frecuencia: 20%
Descripción: Publicación en portales premium + headhunters
Prioridad: Alta

V2: Candidatos referidos
Contexto: Paso 3 (recibir CVs)
Frecuencia: 15%
Descripción: Empleados pueden referir, van directo a entrevista
Prioridad: Alta

=== PAIN POINTS (P) ===
P1: Revisión manual CVs
Frecuencia: 100%
Tiempo: 3 horas/posición
Error rate: 20%
Impacto: RRHH saturado
Prioridad: Crítica

P2: Sin sistema ATS
Contexto: General
Problema: Usando Excel para gestionar aplicaciones
Workaround: Hoja de cálculo manual
Prioridad: Alta

=== CONOCIMIENTO TÁCITO (K) ===
K1: Criterios scoring por tipo puesto
Comercial: Exp50% Form30% Ref20%
Técnico: Form60% Exp30% Ref10%

K2: Criterios "fit" equipo
Definición: Subjetivo
Proceso: Feeling + referencias
Riesgo: Sesgo inconsistencia

=== ASUNCIONES (A) ===
A1: Referencias son confiables
A2: Scoring manual es objetivo
A3: Fit se puede evaluar objetivamente
```

---

### Historia Principal

**Facilitador:** "Carlos, basándome en lo que me has contado, la historia principal sería así:"

```
Historia Principal - Contratación (Happy Path)

1. `RRHH identifica necesidad de personal`
2. `RRHH publica oferta en portales de empleo`
3. `Candidatos envían CVs`
4. `Sistema ATS registra aplicaciones`
5. `Recruiter revisa CVs según criterios`
6. `Recruiter selecciona candidatos para entrevista`
7. `RRHH programa entrevistas`
8. `Candidatos asisten a entrevistas`
9. `Entrevistadores evalúan candidatos`
10. `RRHH selecciona candidato final`
11. `RRHH prepara contrato`
12. `Candidato firma contrato`
13. `RRHH registra empleado en sistema`
14. `Empleado empieza a trabajar`

Duración típica: 3-4 semanas
Punto crítico: Paso 5 (revisión CVs)
```

---

## Sesión 3: Proceso de Órdenes de Trabajo

### Contexto
**Objetivo:** Modelar proceso de órdenes desde solicitud hasta cierre
**Participantes:**
- Facilitador (tú)
- Experto del dominio: Responsable Operaciones (Ana)

### Inicio

**Facilitador:** "Ana, queremos entender el proceso completo de órdenes de trabajo. Cuéntame desde que llega una solicitud hasta que cerramos la orden."

**Ana:** "Cuando un cliente solicita un servicio, el comercial crea una orden preliminar."

**Facilitador:** "¿Qué incluye esa orden?"

**Ana:** "Datos del cliente, tipo de servicio, urgencia..."

**Facilitador:** "¿Y después?"

**Ana:** "Yo reviso la orden y asigno un técnico."

**Facilitador:** "¿Cómo eliges qué técnico?"

**Ana:** "Según disponibilidad y experiencia en ese tipo de trabajo."

**Facilitador:** *(detectando conocimiento tácito)* "¿Cómo weigh disponibilidad vs experiencia?"

**Ana:** "Disponibilidad 60%, experiencia 40%."

**Facilitador:** "¿Eso está definido?"

**Ana:** "No, es lo que hemos visto que funciona mejor."

---

### Detección de Plot Holes

**Facilitador:** "Ana, cuando asignas el técnico, ¿cómo se entera él?"

**Ana:** "Le llega una notificación en su tablet."

**Facilitador:** "¿Y entonces qué pasa?"

**Ana:** "Va al lugar y hace el trabajo."

**Facilitador:** *(detectando gap)* "¿Y después de hacer el trabajo?"

**Ana:** "Completa el parte de trabajo en el tablet."

**Facilitador:** "¿Y eso sube automáticamente al sistema?"

**Ana:** "Sí, cuando tiene señal."

**Facilitador:** *(detectando dependencia)* "¿Y si no tiene señal?"

**Ana:** "Ah, entonces tiene que volver a la oficina."

**Facilitador:** *(anotando)*
```
PLOT HOLE IDENTIFICADO:
Gap: Sincronización tablet ↔ sistema
Dependencia: Conexión a internet
Frecuencia: 30% ubicaciones sin buena señal
Impacto: Técnico debe retornar a oficina
```

---

### Knowledge Crunching - Reglas No Escritas

**Facilitador:** "Ana, mencionaste urgencia. ¿Cómo define urgencia?"

**Ana:** "Depende, pero si es cliente importante o una emergencia."

**Facilitador:** "¿Qué hace que un cliente sea 'importante'?"

**Ana:** "Volumen de compra, o si es estratégico."

**Facilitador:** "¿Y para emergencias?"

**Ana:** "Si es algo que no puede esperar al día siguiente."

**Facilitador:** "¿Y cómo afecta a la asignación?"

**Ana:** "Urgentes van al técnico disponible más cercano, aunque no sea el más experimentado."

**Facilitador:** *(extrayendo)*
```
REGLAS NO ESCRITAS:

R1: Priorización urgencias
Criterio 1: Disponibilidad técnico (50%)
Criterio 2: Proximidad geográfica (50%)
Experiencia: Ignorada en urgencias

R2: Clientes importantes
Criterio: Volumen >€50k/año o estratégico
Beneficio: Prioridad en asignación

R3: Definición emergencia
- No puede esperar al día siguiente
- Técnico senior si disponible
- Costo secundario a velocidad
```

---

### Identificación de Pain Points

**Facilitador:** "Ana, el técnico completa el parte en el tablet. ¿Va bien eso?"

**Ana:** "Sí, pero luego tiene que venir a la oficina a pasar los datos al sistema de facturación."

**Facilitador:** *(detectando problema)* "¿Por qué? ¿No se sincroniza automáticamente?"

**Ana:** "La sincronización no funciona bien, entonces prefiere meterlos él mismo para estar seguro."

**Facilitador:** "¿Con qué frecuencia pasa?"

**Ana:** "Siempre, nunca confía en la sincronización."

**Facilitador:** "¿Cuánto tiempo le toma?"

**Ana:** "20-30 minutos."

**Facilitador:** *(calculando impacto)*
```
P1: Transcripción manual tablet → sistema facturación
Frecuencia: 100%
Tiempo perdido: 20-30 min/orden
Causa: Desconfianza en sincronización
Impacto: Técnico no disponible 30 min/orden
```

---

### Exploración de Conocimiento Tácito

**Facilitador:** "Ana, cuando revisa las órdenes para asignar, ¿qué más considera además de disponibilidad y experiencia?"

**Ana:** "La ubicación, claro."

**Facilitador:** "¿Cómo weight la ubicación?"

**Ana:** "Depende de la urgencia. Si es normal, ubicación 20%. Si es urgente, 50%."

**Facilitador:** "¿Y el tipo de trabajo?"

**Ana:** "Eso ya está en experiencia."

**Facilitador:** "¿Y la carga de trabajo actual del técnico?"

**Ana:** "Ah sí, también. Si un técnico ya tiene muchas órdenes, lo evitamos."

**Facilitador:** "¿Cómo weight eso?"

**Ana:** "Carga de trabajo 15% cuando no es urgente."

**Facilitador:** *(documentando criterios completos)*
```
CRITERIOS ASIGNACIÓN TÉCNICO (No urgente):
- Disponibilidad: 60%
- Experiencia: 20%
- Ubicación: 20%
- Carga trabajo: 15%
Total: 115% (carga trabajo es factor limitante)

CRITERIOS ASIGNACIÓN TÉCNICO (Urgente):
- Disponibilidad: 50%
- Proximidad: 50%
```

---

### Validación de Supuestos

**Facilitador:** "Ana, mencionaste que la sincronización no funciona bien. ¿Qué pasa exactamente?"

**Ana:** "A veces sube los datos, a veces no. Es impredecible."

**Facilitador:** "¿Han intentado solucionarlo?"

**Ana:** "Sí, el departamento de IT dice que es problema de cobertura."

**Facilitador:** "¿Y han medido la tasa de éxito?"

**Ana:** "No, pero los técnicos lo han comentado."

**Facilitador:** *(detectando asunción)*
```
ASUNCIÓN:
A1: Sincronización tablet no confiable
Evidencia: Percepción técnicos
Datos: Sin medición objetiva
Riesgo: Puede ser más confiable de lo que creen
```

---

### Anotaciones Finales

**Facilitador:** *(organizando)*
```
ANOTACIONES - Proceso Órdenes de Trabajo

=== VARIACIONES (V) ===
V1: Orden urgente
Contexto: Paso 3 (asignar técnico)
Frecuencia: 30%
Descripción: Prioridad disponibilidad + proximidad, ignora experiencia
Prioridad: Alta

V2: Cliente importante
Contexto: Paso 3 (asignar técnico)
Frecuencia: 20%
Descripción: Técnicos senior asignados
Prioridad: Media

=== PAIN POINTS (P) ===
P1: Transcripción manual
Contexto: Paso 7 (completar parte)
Frecuencia: 100%
Tiempo: 20-30 min/orden
Causa: Desconfianza sincronización
Impacto: Técnico no disponible
Prioridad: Crítica

P2: Sincronización tablet
Contexto: Paso 6 (sincronizar datos)
Frecuencia: Desconocida (percepción: frecuente)
Problema: Datos no suben al sistema
Causa: Cobertura internet
Prioridad: Alta

=== CONOCIMIENTO TÁCITO (K) ===
K1: Criterios asignación por urgencia
Normal: Disp60% Exp20% Ubic20% Carga15%
Urgente: Disp50% Proxim50%

K2: Definición cliente importante
Criterio: Volumen >€50k/año o estratégico
Beneficio: Técnicos senior

=== ASUNCIONES (A) ===
A1: Sincronización tablet <50% éxito
A2: Técnicos prefieren control manual
A3: Cobertura internet determina éxito sincronización

=== PREGUNTAS (Q) ===
Q1: Tasa real éxito sincronización
Pregunta: ¿Qué % de sincronizaciones fallan realmente?
Estado: Pendiente medición
```

---

### Historia Principal Final

```
Historia Principal - Órdenes de Trabajo (Happy Path)

1. `Cliente solicita servicio`
2. `Comercial recibe solicitud`
3. `Comercial crea orden preliminar`
4. `Responsable operaciones revisa orden`
5. `Responsable operaciones asigna técnico`
6. `Técnico recibe notificación en tablet`
7. `Técnico se desplaza al lugar`
8. `Técnico realiza el servicio`
9. `Técnico completa parte de trabajo en tablet`
10. `Técnico sincroniza datos con sistema`
11. `Sistema genera factura automáticamente`
12. `Administrativo envía factura al cliente`
13. `Cliente recibe y paga factura`
14. `Responsable operaciones cierra orden`

Duración típica: 2-3 días
Punto crítico: Paso 10 (sincronización)
```

---

## Lecciones Aprendidas de las Sesiones

### Técnicas Exitosas

#### 1. Escucha Activa + Anotación Inmediata
- ✅ Anotar en tiempo real mantiene flujo
- ✅ Formato estándar facilita organización
- ✅ Códigos simples (V1, P1) son efectivos

#### 2. Preguntas de Profundización
- ✅ "¿Con qué frecuencia?" → Métricas
- ✅ "¿Cómo exactamente?" → Plot holes
- ✅ "¿Por qué?" → Causa raíz
- ✅ "¿Qué más?" → Conocimiento tácito

#### 3. Separación Clara
- ✅ Historia principal = Happy path
- ✅ Anotaciones = Todo lo complejo
- ✅ Referencias cruzadas = Contexto claro

#### 4. Validación Continua
- ✅ Repetición para confirmar
- ✅ "¿Refleja el 80% de casos?"
- ✅ "¿Falta algo importante?"

### Errores a Evitar

❌ **No interrumpir flujo excesivo**
- Permitir narración completa primero
- Preguntas después, no durante

❌ **Mezclar solución con problema**
- Solo documentar, no proponer
- Focus en entender, no en arreglar

❌ **No cuantificar pain points**
- Siempre preguntar frecuencia
- Calcular impacto en tiempo/recursos

❌ **Aceptar generalidades**
- "Siempre", "nunca", "normalmente" → Profundizar
- Ejemplos específicos > Reglas generales

### Factores de Éxito

1. **Ambiente seguro** - "Esto es normal", "Entiendo el problema"
2. **Curiosidad genuina** - Realmente querer entender
3. **Paciencia** - Knowledge crunching toma tiempo
4. **Organización** - Anotaciones sistemáticas
5. **Validación** - Confirmar entendimiento

**Recuerda:** La facilitación exitosa es 70% escuchar, 20% preguntar, 10% documentar. Tu trabajo es extraer la sabiduría del experto, no imponer tu estructura.
