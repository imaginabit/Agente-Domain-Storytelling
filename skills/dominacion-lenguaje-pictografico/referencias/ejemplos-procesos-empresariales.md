# Ejemplos de Procesos Empresariales

Este documento contiene ejemplos reales de análisis de procesos empresariales usando lenguaje pictográfico.

## Proceso de Contratación de Empleados

### Texto Original
"El departamento de RRHH publica la oferta de empleo en el portal web. Los candidatos envían sus currículums a través del formulario online. El sistema ATS registra automáticamente todas las aplicaciones. El recruiter revisa los CVs y selecciona los candidatos preseleccionados. El responsable de RRHH проводит las entrevistas personales. El candidato seleccionado firma el contrato laboral."

### Análisis Completo

**Actores identificados:**
- departamento de RRHH
- candidatos
- sistema ATS
- recruiter
- responsable de RRHH
- candidato seleccionado

**Objetos de trabajo:**
- oferta de empleo
- portal web
- currículums
- formulario online
- aplicaciones
- CVs
- candidatos preseleccionados
- entrevistas personales
- contrato laboral

**Actividades:**
- publicar, enviar, registrar, revisar, seleccionar, проводит (realizar), firmar

**Estructura de Tripletas:**
1. `departamento de RRHH → publica → oferta de empleo`
2. `departamento de RRHH → publica → oferta de empleo en portal web`
3. `candidatos → envían → currículums`
4. `candidatos → envían → currículums a través de formulario online`
5. `sistema ATS → registra → aplicaciones`
6. `sistema ATS → registra → automáticamente aplicaciones`
7. `recruiter → revisa → CVs`
8. `recruiter → selecciona → candidatos preseleccionados`
9. `responsable de RRHH → realiza → entrevistas personales`
10. `candidato seleccionado → firma → contrato laboral`

---

## Proceso de Gestión de Órdenes de Compra

### Texto Original
"El departamento de compras recibe la solicitud de materiales del área de producción. El buyer analiza la solicitud y busca proveedores en el sistema de proveedores. El sistema genera automáticamente 3 cotizaciones. El proveedor envía la cotización con precios y plazos de entrega. El buyer compara las cotizaciones y selecciona la mejor opción. El responsable de compras aprueba la orden de compra. El sistema envía la orden aprobada al proveedor seleccionado."

### Análisis Completo

**Actores identificados:**
- departamento de compras
- área de producción
- buyer
- sistema de proveedores
- sistema
- proveedor
- responsable de compras

**Objetos de trabajo:**
- solicitud de materiales
- proveedores
- cotizaciones
- precios
- plazos de entrega
- orden de compra

**Actividades:**
- recibir, analizar, buscar, generar, enviar, comparar, seleccionar, aprobar

**Estructura de Tripletas:**
1. `área de producción → envía → solicitud de materiales`
2. `departamento de compras ← recibe ← solicitud de materiales`
3. `buyer → analiza → solicitud de materiales`
4. `buyer → busca → proveedores en sistema de proveedores`
5. `sistema → genera → cotizaciones`
6. `sistema → genera → automáticamente 3 cotizaciones`
7. `proveedor → envía → cotización con precios`
8. `proveedor → envía → cotización con plazos de entrega`
9. `buyer → compara → cotizaciones`
10. `buyer → selecciona → mejor opción`
11. `responsable de compras → aprueba → orden de compra`
12. `sistema → envía → orden aprobada al proveedor seleccionado`

---

## Proceso de Facturación

### Texto Original
"Cuando se completa una orden de trabajo, el técnico genera el parte de trabajo. El sistema ERP calcula automáticamente los costes de materiales y mano de obra. El departamento administrativo crea la factura basada en el parte de trabajo. El cliente recibe la factura por email. Si el cliente aprueba la factura, el sistema registra el cobro. Si no hay respuesta en 30 días, el sistema envía un recordatorio de pago."

### Análisis Completo

**Actores identificados:**
- técnico
- sistema ERP
- departamento administrativo
- cliente
- sistema

**Objetos de trabajo:**
- orden de trabajo
- parte de trabajo
- costes de materiales
- mano de obra
- factura
- cobro

**Actividades:**
- completar, generar, calcular, crear, recibir, aprobar, registrar, enviar, responder

**Estructura de Tripletas:**
1. `técnico → completa → orden de trabajo`
2. `técnico → genera → parte de trabajo`
3. `sistema ERP → calcula → costes de materiales`
4. `sistema ERP → calcula → mano de obra`
5. `departamento administrativo → crea → factura`
6. `departamento administrativo → crea → factura basada en parte de trabajo`
7. `cliente ← recibe ← factura por email`
8. `cliente → aprueba → factura`
9. `sistema → registra → cobro`
10. `sistema → envía → recordatorio de pago (si no hay respuesta en 30 días)`
11. `cliente → responde → factura (implícito)`

---

## Proceso de Control de Calidad

### Texto Original
"Cada producto manufactured pasa por el control de calidad. El inspector de calidad realiza pruebas según el plan de inspección. Si el producto cumple los estándares, se etiqueta como 'APROBADO' y se envía al almacén. Si no cumple los estándares, se etiqueta como 'RECHAZADO' y se envía al área de no conformidades. El responsable de calidad revisa semanalmente los productos rechazados para identificar patrones."

### Análisis Completo

**Actores identificados:**
- inspector de calidad
- producto manufactured
- plan de inspección
- responsable de calidad

**Objetos de trabajo:**
- productos
- estándares
- etiqueta 'APROBADO'
- almacén
- etiqueta 'RECHAZADO'
- área de no conformidades
- productos rechazados
- patrones

**Actividades:**
- pasar, realizar, cumple, etiqueta, envía, revisa, identifica

**Estructura de Tripletas:**
1. `producto manufactured → pasa → control de calidad`
2. `inspector de calidad → realiza → pruebas`
3. `inspector de calidad → realiza → pruebas según plan de inspección`
4. `producto → cumple → estándares`
5. `producto → etiqueta como 'APROBADO'`
6. `producto → envía → almacén`
7. `producto → etiqueta como 'RECHAZADO'`
8. `producto → envía → área de no conformidades`
9. `responsable de calidad → revisa → productos rechazados`
10. `responsable de calidad → revisa → semanalmente productos rechazados`
11. `responsable de calidad → identifica → patrones`

---

## Proceso de Atención al Cliente

### Texto Original
"El cliente contacta al servicio de atención al cliente a través del chat online. El agente de soporte recibe la consulta y la clasifica según su tipo. Si es una consulta técnica, la deriva al departamento de IT. Si es una consulta comercial, la deriva al departamento de ventas. El departamento correspondiente responde al cliente. El agente de soporte registra la consulta y la respuesta en el CRM. El supervisor revisa mensualmente la calidad de las respuestas."

### Análisis Completo

**Actores identificados:**
- cliente
- servicio de atención al cliente
- agente de soporte
- departamento de IT
- departamento de ventas
- departamento correspondiente
- supervisor

**Objetos de trabajo:**
- consulta
- tipo
- respuesta
- calidad de las respuestas

**Actividades:**
- contacta, recibe, clasifica, deriva, responde, registra

**Estructura de Tripletas:**
1. `cliente → contacta → servicio de atención al cliente`
2. `cliente → contacta → servicio de atención al cliente a través del chat online`
3. `agente de soporte ← recibe ← consulta`
4. `agente de soporte → clasifica → consulta según tipo`
5. `consulta → deriva → departamento de IT (si es técnica)`
6. `consulta → deriva → departamento de ventas (si es comercial)`
7. `departamento correspondiente → responde → cliente`
8. `agente de soporte → registra → consulta en CRM`
9. `agente de soporte → registra → respuesta en CRM`
10. `supervisor → revisa → calidad de las respuestas`
11. `supervisor → revisa → mensualmente calidad de las respuestas`
