# Casos de Uso - Dominio Órdenes de Trabajo

Ejemplos específicos de análisis pictográfico para procesos de órdenes de trabajo en el contexto de HMGest.

## Proceso de Creación de Orden de Trabajo

### Texto Original
"El cliente solicita un servicio de mantenimiento. El departamento comercial crea una orden de trabajo preliminar con los datos del cliente y descripción del servicio. El responsable de operaciones revisa la orden y asigna un técnico especializado. El técnico recibe la orden en su tablet y se desplaza al lugar de trabajo. Una vez finalizado el servicio, el técnico completa el parte de trabajo detallando las tareas realizadas y materiales utilizados. El cliente firma el parte de trabajo confirmando la conformidad."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- cliente
- departamento comercial
- responsable de operaciones
- técnico
- parte de trabajo

**Objetos específicos de órdenes:**
- servicio de mantenimiento
- orden de trabajo preliminar
- datos del cliente
- descripción del servicio
- técnico especializado
- tablet
- lugar de trabajo
- tareas realizadas
- materiales utilizados
- parte de trabajo
- conformidad

**Actividades específicas de órdenes:**
- solicita, crea, revisa, asigna, recibe, desplaza, completa, firma, confirma

**Estructura de Tripletas:**
1. `cliente → solicita → servicio de mantenimiento`
2. `departamento comercial → crea → orden de trabajo preliminar`
3. `departamento comercial → crea → orden de trabajo con datos del cliente`
4. `departamento comercial → crea → orden de trabajo con descripción del servicio`
5. `responsable de operaciones → revisa → orden de trabajo`
6. `responsable de operaciones → asigna → técnico especializado`
7. `técnico ← recibe → orden en tablet`
8. `técnico → se desplaza → lugar de trabajo`
9. `técnico → completa → parte de trabajo`
10. `técnico → completa → parte de trabajo detallando tareas realizadas`
11. `técnico → completa → parte de trabajo con materiales utilizados`
12. `cliente → firma → parte de trabajo`
13. `cliente → confirma → conformidad`

---

## Proceso de Planificación de Recursos

### Texto Original
"Cada semana, el planificador revisa las órdenes de trabajo pendientes. El sistema muestra la disponibilidad de técnicos y materiales. El planificador asigna recursos a cada orden considerando la prioridad, duración estimada y ubicación. Si hay conflictos de recursos, el planificador reprograma las órdenes. El sistema envía la planificación semanal a todos los técnicos. Cada técnico recibe su agenda con las órdenes asignadas."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- planificador
- sistema
- técnicos
- órdenes de trabajo

**Objetos específicos de órdenes:**
- órdenes pendientes
- disponibilidad de técnicos
- materiales
- recursos
- prioridad
- duración estimada
- ubicación
- conflictos de recursos
- planificación semanal
- agenda

**Actividades específicas de órdenes:**
- revisa, muestra, asigna, reprograma, envía, recibe

**Estructura de Tripletas:**
1. `planificador → revisa → órdenes pendientes`
2. `sistema → muestra → disponibilidad de técnicos`
3. `sistema → muestra → disponibilidad de materiales`
4. `planificador → asigna → recursos a orden`
5. `planificador → asigna → recursos considerando prioridad`
6. `planificador → asigna → recursos considerando duración estimada`
7. `planificador → asigna → recursos considerando ubicación`
8. `planificador → reprograma → órdenes (SI hay conflictos)`
9. `sistema → envía → planificación semanal a técnicos`
10. `técnicos ← reciben → agenda con órdenes asignadas`

---

## Proceso de Control de Materiales

### Texto Original
"Cuando el técnico inicia una orden, el sistema verifica el stock de materiales necesarios. Si hay stock suficiente, el almacén prepara el material y el técnico lo retira. Si no hay stock suficiente, el sistema genera automáticamente una solicitud de compra. El responsable de compras revisa la solicitud y emite una orden de compra al proveedor. El proveedor entrega los materiales y el sistema actualiza el stock. El técnico procede con la orden usando los materiales disponibles."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- técnico
- sistema
- almacén
- responsable de compras
- proveedor

**Objetos específicos de órdenes:**
- orden
- stock de materiales
- materiales necesarios
- solicitud de compra
- orden de compra
- materiales

**Actividades específicas de órdenes:**
- inicia, verifica, prepara, retira, genera, revisa, emite, entrega, actualiza, procede

**Estructura de Tripletas:**
1. `técnico → inicia → orden`
2. `sistema → verifica → stock de materiales`
3. `sistema → verifica → stock de materiales necesarios`
4. `almacén → prepara → material`
5. `técnico → retira → material`
6. `sistema → genera → solicitud de compra (SI no hay stock suficiente)`
7. `responsable de compras → revisa → solicitud`
8. `responsable de compras → emite → orden de compra al proveedor`
9. `proveedor → entrega → materiales`
10. `sistema → actualiza → stock`
11. `técnico → procede → orden con materiales disponibles`

---

## Proceso de Certificación y Calidad

### Texto Original
"Tras completar las tareas de la orden, el técnico realiza las pruebas de calidad según el protocolo. El inspector de calidad verifica que el trabajo cumple los estándares requeridos. Si cumple los estándares, certifica la orden como APROBADA. Si no cumple, la marca como NO CONFORME y genera una incidencia. El cliente recibe un email con el certificado de calidad o el informe de no conformidad. El responsable de calidad revisa semanalmente las incidencias para identificar patrones de problemas."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- técnico
- protocolo
- inspector de calidad
- sistema
- cliente
- responsable de calidad

**Objetos específicos de órdenes:**
- tareas de la orden
- pruebas de calidad
- estándares requeridos
- certificado de calidad
- incidencia
- email
- informe de no conformidad
- incidencias
- patrones de problemas

**Actividades específicas de órdenes:**
- completa, realiza, verifica, certifica, marca, genera, recibe, revisa, identifica

**Estructura de Tripletas:**
1. `técnico → completa → tareas de la orden`
2. `técnico → realiza → pruebas de calidad`
3. `técnico → realiza → pruebas según protocolo`
4. `inspector de calidad → verifica → trabajo`
5. `inspector de calidad → verifica → trabajo cumple estándares requeridos`
6. `inspector de calidad → certifica → orden como APROBADA (SI cumple estándares)`
7. `inspector de calidad → marca → orden como NO CONFORME (SI no cumple)`
8. `inspector de calidad → genera → incidencia`
9. `cliente ← recibe → email con certificado de calidad`
10. `cliente ← recibe → email con informe de no conformidad`
11. `responsable de calidad → revisa → incidencias semanalmente`
12. `responsable de calidad → identifica → patrones de problemas`

---

## Proceso de Facturación Automática

### Texto Original
"Cuando la orden se marca como completada, el sistema genera automáticamente la factura. El sistema calcula el coste basándose en las horas trabajadas, materiales utilizados y desplazamiento. El departamento administrativo revisa la factura antes de enviarla al cliente. Si la factura supera los 1000€, requiere aprobación del director. Una vez aprobada, el sistema envía la factura al cliente por email y registra la factura en contabilidad."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- sistema
- departamento administrativo
- director
- cliente
- contabilidad

**Objetos específicos de órdenes:**
- orden completada
- factura
- horas trabajadas
- materiales utilizados
- desplazamiento
- aprobación del director
- email

**Actividades específicas de órdenes:**
- marca, genera, calcula, revisa, envía, requiere, aprueba, registra

**Estructura de Tripletas:**
1. `sistema → marca → orden como completada`
2. `sistema → genera → factura automáticamente`
3. `sistema → calcula → coste basándose en horas trabajadas`
4. `sistema → calcula → coste basándose en materiales utilizados`
5. `sistema → calcula → coste basándose en desplazamiento`
6. `departamento administrativo → revisa → factura`
7. `departamento administrativo → revisa → factura antes de enviarla al cliente`
8. `director → aprueba → factura (SI factura > 1000€)`
9. `sistema → envía → factura al cliente por email`
10. `contabilidad ← registra → factura`

---

## Proceso de Seguimiento de Incidencias

### Texto Original
"Si durante la ejecución de una orden surge una incidencia, el técnico la documenta inmediatamente en la aplicación móvil. El sistema asigna automáticamente un número de incidencia y envía alerta al supervisor. El supervisor evalúa la incidencia y decide si requiere parada de la orden o puede continuar. Si requiere parada, asigna un especialista para resolverla. Una vez resuelta, el especialista actualiza el estado y la orden continúa su ejecución."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- técnico
- aplicación móvil
- sistema
- supervisor
- especialista

**Objetos específicos de órdenes:**
- incidencia
- número de incidencia
- alerta
- estado

**Actividades específicas de órdenes:**
- surge, documenta, asigna, envía, evalúa, decide, resuelve, actualiza, continúa

**Estructura de Tripletas:**
1. `técnico → documenta → incidencia en aplicación móvil`
2. `técnico → documenta → incidencia inmediatamente`
3. `sistema → asigna → número de incidencia`
4. `sistema → envía → alerta al supervisor`
5. `supervisor → evalua → incidencia`
6. `supervisor → decide → si requiere parada de la orden`
7. `supervisor → decide → si puede continuar (evaluación implícita)`
8. `supervisor → asigna → especialista para resolver incidencia`
9. `especialista → resuelve → incidencia`
10. `especialista → actualiza → estado`
11. `orden → continúa → ejecución`

---

## Proceso de Cierre de Orden

### Texto Original
"Una vez certificadas las tareas y facturada la orden, el técnico archiva toda la documentación en el sistema. El sistema genera automáticamente el informe final con resumen de tareas, materiales, tiempos y costes. El responsable de operaciones revisa el informe y cierra la orden en el sistema. El cliente recibe una encuesta de satisfacción por email. RRHH registra las horas trabajadas en la nóminas del técnico. El sistema archiva la orden como HISTÓRICA para consultas futuras."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- técnico
- sistema
- responsable de operaciones
- cliente
- RRHH

**Objetos específicos de órdenes:**
- documentación
- informe final
- resumen de tareas
- materiales
- tiempos
- costes
- encuesta de satisfacción
- horas trabajadas
- nóminas
- orden HISTÓRICA

**Actividades específicas de órdenes:**
- archiva, genera, revisa, cierra, recibe, registra

**Estructura de Tripletas:**
1. `técnico → archiva → documentación en sistema`
2. `sistema → genera → informe final automáticamente`
3. `sistema → genera → informe con resumen de tareas`
4. `sistema → genera → informe con materiales`
5. `sistema → genera → informe con tiempos y costes`
6. `responsable de operaciones → revisa → informe final`
7. `responsable de operaciones → cierra → orden en sistema`
8. `cliente ← recibe → encuesta de satisfacción por email`
9. `RRHH → registra → horas trabajadas en nóminas del técnico`
10. `sistema → archiva → orden como HISTÓRICA para consultas futuras`

---

## Proceso de Gestión de Garantías

### Texto Original
"Cada orden completada activa automáticamente una garantía de 6 meses. El sistema registra la fecha de finalización y programa revisiones periódicas. Tres meses después, el sistema envía un recordatorio al cliente para verificar el correcto funcionamiento. Si el cliente reporta un problema durante el período de garantía, se crea una nueva orden prioritaria sin coste. El técnico asignado diagnostica el problema y realiza la reparación necesaria bajo garantía."

### Análisis de Órdenes

**Actores específicos de órdenes:**
- sistema
- cliente
- técnico asignado

**Objetos específicos de órdenes:**
- orden completada
- garantía de 6 meses
- fecha de finalización
- revisiones periódicas
- recordatorio
- correcto funcionamiento
- problema
- orden prioritaria
- diagnóstico
- reparación necesaria

**Actividades específicas de órdenes:**
- activa, registra, programa, envía, verifica, reporta, crea, diagnostica, realiza

**Estructura de Tripletas:**
1. `sistema → activa → garantía de 6 meses automáticamente`
2. `sistema → registra → fecha de finalización`
3. `sistema → programa → revisiones periódicas`
4. `sistema → envía → recordatorio al cliente`
5. `sistema → envía → recordatorio 3 meses después`
6. `cliente → verifica → correcto funcionamiento`
7. `cliente → reporta → problema durante período de garantía`
8. `sistema → crea → orden prioritaria sin coste`
9. `técnico asignado → diagnostica → problema`
10. `técnico asignado → realiza → reparación necesaria bajo garantía`

---

## Patrones Específicos en Órdenes de Trabajo

### Verbos Típicos de Órdenes
- crea, asigna, ejecuta, completa, verifica, certifica, factura, archiva, cierra, asigna, programa, revisa, aprueba, genera, actualiza, registra, controla, inspecciona, prueba, valida, documenta, informa, notifica, alerta, resuelve

### Objetos Típicos de Órdenes
- orden de trabajo, técnico, cliente, parte de trabajo, materiales, factura, certificado, incidencia, garantía, planificación, recursos, tiempos, costes, calidad, conformidad, documentación

### Actores Típicos de Órdenes
- técnico, supervisor, responsable de operaciones, planificador, inspector de calidad, departamento comercial, cliente, sistema, almacén, proveedor, responsable de compras
