# Casos de Uso - Dominio RRHH

Ejemplos específicos de análisis pictográfico para procesos de Recursos Humanos en el contexto de HMGest.

## Proceso de Alta de Empleado

### Texto Original
"Cuando se incorpora un nuevo empleado, el departamento de RRHH crea el expediente en el sistema. El responsable de RRHH completa los datos personales del empleado y genera el contrato laboral. El nuevo empleado firma el contrato digitalmente. RRHH registra al empleado en la nóminas del mes siguiente. El sistema asigna automáticamente un número de empleado y crea las credenciales de acceso al sistema. El supervisor directo recibe una notificación para programar la jornada de formación inicial."

### Análisis RRHH

**Actores específicos de RRHH:**
- departamento de RRHH
- responsable de RRHH
- nuevo empleado
- sistema
- supervisor directo

**Objetos específicos de RRHH:**
- expediente
- datos personales del empleado
- contrato laboral
- credenciales de acceso
- número de empleado
- jornada de formación inicial
- nóminas

**Actividades específicas de RRHH:**
- incorpora, crea, completa, genera, firma, registra, asigna, notifica, programa

**Estructura de Tripletas:**
1. `departamento de RRHH → crea → expediente`
2. `responsable de RRHH → completa → datos personales del empleado`
3. `responsable de RRHH → genera → contrato laboral`
4. `nuevo empleado → firma → contrato laboral`
5. `nuevo empleado → firma → contrato laboral digitalmente`
6. `RRHH → registra → empleado en nóminas`
7. `RRHH → registra → empleado en nóminas del mes siguiente`
8. `sistema → asigna → número de empleado`
9. `sistema → asigna → automáticamente número de empleado`
10. `sistema → crea → credenciales de acceso al sistema`
11. `supervisor directo ← recibe → notificación`
12. `supervisor directo → programa → jornada de formación inicial`

---

## Proceso de Solicitud de Vacaciones

### Texto Original
"El empleado accede al sistema de RRHH y solicita vacaciones indicando las fechas. El sistema valida que el empleado tenga días disponibles. Si hay días disponibles, la solicitud se envía al supervisor. El supervisor revisa la solicitud considerando la carga de trabajo del departamento. El supervisor aprueba o rechaza la solicitud. Si aprueba, el sistema actualiza el calendario de vacaciones y envía confirmación al empleado. RRHH recibe una copia de la solicitud aprobada para su archivo."

### Análisis RRHH

**Actores específicos de RRHH:**
- empleado
- sistema de RRHH
- supervisor
- RRHH

**Objetos específicos de RRHH:**
- solicitud de vacaciones
- fechas
- días disponibles
- carga de trabajo
- calendario de vacaciones
- solicitud aprobada
- copia de la solicitud

**Actividades específicas de RRHH:**
- accede, solicita, indica, valida, envía, revisa, aprueba, rechaza, actualiza, confirma, archiva

**Estructura de Tripletas:**
1. `empleado → accede → sistema de RRHH`
2. `empleado → solicita → vacaciones`
3. `empleado → indica → fechas`
4. `sistema de RRHH → valida → días disponibles`
5. `empleado → tiene → días disponibles (validación implícita)`
6. `sistema de RRHH → envía → solicitud al supervisor`
7. `supervisor → revisa → solicitud`
8. `supervisor → revisa → solicitud considerando carga de trabajo del departamento`
9. `supervisor → aprueba → solicitud (SI cumple condiciones)`
10. `supervisor → rechaza → solicitud (SI no cumple condiciones)`
11. `sistema de RRHH → actualiza → calendario de vacaciones`
12. `sistema de RRHH → envía → confirmación al empleado`
13. `RRHH ← recibe → copia de la solicitud aprobada`
14. `RRHH → archiva → copia de la solicitud`

---

## Proceso de Evaluación de Desempeño

### Texto Original
"Anualmente, el responsable de RRHH programa las evaluaciones de desempeño para todos los empleados. El sistema envía una notificación al empleado y a su supervisor. El empleado completa la autoevaluación en el formulario online. El supervisor completa la evaluación del empleado. El responsable de RRHH revisa ambas evaluaciones y programa la reunión de feedback. Durante la reunión, supervisor y empleado discuten los resultados y definen objetivos para el próximo año. RRHH registra los resultados en el expediente del empleado."

### Análisis RRHH

**Actores específicos de RRHH:**
- responsable de RRHH
- sistema
- empleado
- supervisor

**Objetos específicos de RRHH:**
- evaluaciones de desempeño
- autoevaluación
- formulario online
- evaluación del empleado
- reunión de feedback
- resultados
- objetivos
- expediente del empleado

**Actividades específicas de RRHH:**
- programa, envía, notifica, completa, revisa, discuten, define, registra

**Estructura de Tripletas:**
1. `responsable de RRHH → programa → evaluaciones de desempeño`
2. `responsable de RRHH → programa → evaluaciones para todos los empleados`
3. `sistema → envía → notificación al empleado`
4. `sistema → envía → notificación al supervisor`
5. `empleado → completa → autoevaluación`
6. `empleado → completa → autoevaluación en formulario online`
7. `supervisor → completa → evaluación del empleado`
8. `responsable de RRHH → revisa → autoevaluación`
9. `responsable de RRHH → revisa → evaluación del supervisor`
10. `responsable de RRHH → revisa → ambas evaluaciones`
11. `responsable de RRHH → programa → reunión de feedback`
12. `supervisor → discute → resultados con empleado`
13. `empleado → discute → resultados con supervisor`
14. `supervisor → define → objetivos para próximo año`
15. `empleado → define → objetivos para próximo año`
16. `RRHH → registra → resultados en expediente del empleado`

---

## Proceso de Formación y Certificaciones

### Texto Original
"Cuando un empleado necesita formación, RRHH identifica las necesidades de capacitación. El departamento busca cursos disponibles en el catálogo o plataformas externas. Si encuentra un curso adecuado, RRHH inscribe al empleado. El empleado asiste al curso y realiza los exámenes. La plataforma de formación envía el certificado de finalización a RRHH. RRHH registra la certificación en el expediente del empleado y actualiza sus competencias en el sistema."

### Análisis RRHH

**Actores específicos de RRHH:**
- empleado
- RRHH
- departamento
- plataforma de formación

**Objetos específicos de RRHH:**
- necesidades de capacitación
- cursos disponibles
- catálogo
- plataformas externas
- curso adecuado
- exámenes
- certificado de finalización
- certificación
- competencias

**Actividades específicas de RRHH:**
- necesita, identifica, busca, encuentra, inscribe, asiste, realiza, envía, registra, actualiza

**Estructura de Tripletas:**
1. `empleado → necesita → formación`
2. `RRHH → identifica → necesidades de capacitación`
3. `departamento → busca → cursos disponibles`
4. `departamento → busca → cursos en catálogo`
5. `departamento → busca → cursos en plataformas externas`
6. `departamento → encuentra → curso adecuado`
7. `RRHH → inscribe → empleado al curso`
8. `empleado → asiste → curso`
9. `empleado → realiza → exámenes`
10. `plataforma de formación → envía → certificado de finalización a RRHH`
11. `RRHH → registra → certificación en expediente del empleado`
12. `RRHH → actualiza → competencias en el sistema`

---

## Proceso de Control de Asistencia

### Texto Original
"Diariamente, los empleados registran su entrada y salida usando el sistema de control de presencia. El sistema calcula las horas trabajadas y detecta incidencias como retrasos o salidas anticipadas. El supervisor recibe un reporte diario de las incidencias de su equipo. RRHH consolida los datos de asistencia mensual y genera el informe para nóminas. El sistema alerta automáticamente si un empleado supera el límite de horas extras autorizado."

### Análisis RRHH

**Actores específicos de RRHH:**
- empleados
- sistema de control de presencia
- supervisor
- RRHH
- sistema

**Objetos específicos de RRHH:**
- entrada
- salida
- horas trabajadas
- incidencias
- retrasos
- salidas anticipadas
- reporte diario
- equipo
- datos de asistencia mensual
- informe para nóminas
- límite de horas extras

**Actividades específicas de RRHH:**
- registran, calcula, detecta, recibe, consolida, genera, alerta

**Estructura de Tripletas:**
1. `empleados → registran → entrada`
2. `empleados → registran → salida`
3. `empleados → registran → entrada y salida usando sistema de control de presencia`
4. `sistema de control de presencia → calcula → horas trabajadas`
5. `sistema de control de presencia → detecta → incidencias`
6. `sistema de control de presencia → detecta → retrasos`
7. `sistema de control de presencia → detecta → salidas anticipadas`
8. `supervisor ← recibe → reporte diario`
9. `supervisor ← recibe → reporte de incidencias de su equipo`
10. `RRHH → consolida → datos de asistencia mensual`
11. `RRHH → genera → informe para nóminas`
12. `sistema → alerta → automáticamente si empleado supera límite de horas extras`

---

## Proceso de Cambio de Puesto

### Texto Original
"Cuando se produce una vacante o promoción, RRHH publica la oferta internamente. Los empleados interesados presentan su candidatura. El responsable del área entrevista a los candidatos. El comité de selección evalúa las candidaturas y selecciona al candidato. RRHH prepara el contrato de cambio de puesto. El empleado firma el nuevo contrato. El sistema actualiza los datos del empleado: puesto, departamento, salario y nivel. El nuevo supervisor recibe una notificación de incorporación."

### Análisis RRHH

**Actores específicos de RRHH:**
- RRHH
- empleados interesados
- responsable del área
- comité de selección
- empleado
- sistema
- nuevo supervisor

**Objetos específicos de RRHH:**
- vacante
- promoción
- oferta internamente
- candidatura
- candidatos
- contrato de cambio de puesto
- datos del empleado
- puesto
- departamento
- salario
- nivel
- notificación de incorporación

**Actividades específicas de RRHH:**
- publica, presenta, entrevista, evalúa, selecciona, prepara, firma, actualiza, recibe

**Estructura de Tripletas:**
1. `RRHH → publica → oferta internamente`
2. `RRHH → publica → oferta cuando se produce vacante`
3. `RRHH → publica → oferta para promoción`
4. `empleados interesados → presentan → candidatura`
5. `responsable del área → entrevista → candidatos`
6. `comité de selección → evalua → candidaturas`
7. `comité de selección → selecciona → candidato`
8. `RRHH → prepara → contrato de cambio de puesto`
9. `empleado → firma → nuevo contrato`
10. `sistema → actualiza → datos del empleado`
11. `sistema → actualiza → puesto`
12. `sistema → actualiza → departamento`
13. `sistema → actualiza → salario`
14. `sistema → actualiza → nivel`
15. `nuevo supervisor ← recibe → notificación de incorporación`

---

## Patrones Específicos en RRHH

### Verbos Típicos de RRHH
- contrata, despide, promociona, evalúa, forma, capacita, registra, archiva, actualiza, asigna, programa, notifica, valida, aprueba, autoriza, planifica, organiza, coordina, supervisa, controla, mantiene, gestiona, procesa

### Objetos Típicos de RRHH
- empleado, candidato, contrato, nóminas, vacaciones, formación, evaluación, competencias, expediente, puesto, departamento, salario, jornada, asistencia, incidencias, certificado, capacitación

### Actores Típicos de RRHH
- empleado, supervisor, RRHH, responsable de RRHH, recruiter, responsable de nóminas, director de RRHH, sistema de RRHH, comité de selección, nuevo empleado
