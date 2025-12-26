# Granularidad: Pájaro vs. Mar/Peces

Este documento explica en detalle las dos perspectivas de granularidad en Domain Storytelling, usando las metáforas de "vista de pájaro/cometa" (coarse-grained) y "vista bajo el mar/peces" (fine-grained) para determinar el nivel apropiado de detalle según el contexto.

## Las Dos Perspectivas de Granularidad

### Vista de Pájaro/Cometa (Coarse-Grained)

**Concepto:** Observar el proceso desde una perspectiva elevada, como un pájaro volando alto o una cometa en el cielo.

#### Características de la Vista de Pájaro

| Aspecto | Descripción |
|---------|-------------|
| **Perspectiva** | Desde arriba, vista general |
| **Alcance** | Flujo principal, pasos amplios |
| **Detalle** | Mínimo, solo lo esencial |
| **Actores** | Principales únicamente |
| **Sistemas** | No se mencionan o se agrupan |
| **Excepciones** | No se incluyen |
| **Validaciones** | Implícitas |
| **Número de pasos** | 5-15 pasos típicamente |

#### Qué VES en la Vista de Pájaro

✅ **El río en su conjunto** - Flujo general
✅ **Los puntos principales** - Hitos importantes
✅ **Los actores clave** - Responsables principales
✅ **La dirección general** - De inicio a fin
✅ **Los outcomes** - Resultados finales

#### Qué NO VES en la Vista de Pájaro

❌ **Las piedras del río** - Detalles específicos
❌ **Las corrientes** - Lógica de negocio
❌ **Los peces** - Casos especiales
❌ **La profundidad** - Validaciones internas
❌ **Los obstáculos** - Problemas específicos

#### Analogías para Vista de Pájaro

- 🦅 **Pájaro volando** - Ve el bosque completo, no cada árbol
- 🎈 **Cometa en el cielo** - Ve la ciudad completa, no cada calle
- 🗺️ **Mapa de carreteras** - Ve autopistas, no caminos vecinales
- 📊 **Dashboard ejecutivo** - Ve KPIs, no métricas detalladas
- 🎬 **Trailer de película** - Ve la historia principal, no escenas

---

### Vista de Mar/Peces (Fine-Grained)

**Concepto:** Observar el proceso desde adentro, como nadar bajo el agua y ver cada detalle.

#### Características de la Vista de Mar/Peces

| Aspecto | Descripción |
|---------|-------------|
| **Perspectiva** | Desde adentro, detalle granular |
| **Alcance** | Cada paso, cada acción |
| **Detalle** | Máximo, incluyendo validaciones |
| **Actores** | Todos los involucrados |
| **Sistemas** | Cada sistema/herramienta mencionada |
| **Excepciones** | Incluidas como variaciones |
| **Validaciones** | Explícitas y detalladas |
| **Número de pasos** | 20-100+ pasos típicamente |

#### Qué VES en la Vista de Mar/Peces

✅ **Cada piedra en el río** - Detalles específicos
✅ **Las corrientes** - Lógica de negocio
✅ **Los peces** - Casos especiales
✅ **La profundidad** - Validaciones internas
✅ **Los obstáculos** - Problemas y soluciones
✅ **La temperatura del agua** - Contexto y condiciones

#### Qué NO VES en la Vista de Mar/Peces

❌ **El río en su conjunto** - Puede perderse en detalles
❌ **El panorama general** - Foco en micro
❌ **La dirección** - Puede perder el norte

#### Analogías para Vista de Mar/Peces

- 🐟 **Buceador underwater** - Ve cada pez, coral, roca
- 🔬 **Microscopio** - Ve células, no organismos completos
- 📝 **Código fuente** - Ve cada línea, no arquitectura
- 🛠️ **Manual técnico** - Ve especificaciones, no overview
- 🎥 **Película completa** - Ve cada escena, no solo trailer

---

## Comparación Directa: Pájaro vs. Mar/Peces

### Mismo Proceso, Dos Perspectivas

#### Proceso: "Cliente Solicita Servicio"

##### Vista de Pájaro (Coarse-Grained)
```
1. `Cliente Contacta Empresa`
2. `Comercial Evalúa Solicitud`
3. `Operaciones Ejecuta Servicio`
4. `Cliente Recibe Factura`
5. `Cliente Paga Servicio`

Duración: 2-4 semanas
Nivel: 5 pasos
Audiencia: Ejecutivos
Propósito: Entender flujo general
```

##### Vista de Mar/Peces (Fine-Grained)
```
1. `Cliente Completa Formulario Web`
2. `Sistema Valida Formato Email`
3. `Sistema Verifica Email No Existe`
4. `Sistema Guarda Cliente en DB`
5. `Sistema Envía Email Bienvenida`
6. `Comercial Recibe Notificación CRM`
7. `Comercial Abre Cliente en CRM`
8. `Comercial Revisa Información Cliente`
9. `Comercial Consulta Historial Compras`
10. `Comercial Evalúa Viabilidad Técnica`
11. `Comercial Consulta Disponibilidad`
12. `Comercial Decide Aprobar/Rechazar`
13. `Si Aprueba: Crea Orden Preliminar`
14. `Si Aprueba: Asigna Técnico`
15. `Si Aprueba: Programa Servicio`
16. `Si Aprueba: Envía Confirmación Cliente`
17. `Si Rechaza: Registra Motivo`
18. `Si Rechaza: Llama al Cliente`
...

Duración: 2-4 semanas
Nivel: 50+ pasos
Audiencia: Desarrolladores
Propósito: Implementación técnica
```

---

## Cuándo Usar Cada Perspectiva

### Cuándo Usar Vista de Pájaro (Coarse-Grained)

#### Escenarios Apropiados

**1. Comunicación Ejecutiva**
- Presentaciones a dirección
- Reporting a stakeholders
- Comunicación con clientes
- Aprobaciones de presupuesto

**Ejemplo:**
```
Director: "¿Cuánto tiempo toma el proceso de ventas?"
Tú: "En vista general, son 5 pasos principales que toman 2-4 semanas desde contacto hasta pago."
```

**2. Planificación Estratégica**
- Diseño de procesos
- Roadmap de mejoras
- Análisis de capacidad
- Identificación de cuellos de botella

**Ejemplo:**
```
Planning: "¿Dónde están los cuellos de botella?"
Tú: "Viendo el flujo general, el paso 2 (evaluación) toma 50% del tiempo total."
```

**3. Onboarding/Understanding Inicial**
- Introducir dominio a nuevo equipo
- Training de alto nivel
- Context setting
- Visión general de procesos

**Ejemplo:**
```
Nuevo empleado: "¿Cómo funciona la empresa?"
Tú: "Tenemos 5 procesos principales que verás en detalle después, pero en alto nivel es así..."
```

**4. Comunicación Inter-Departamental**
- Entre equipos diferentes
- Colaboración entre áreas
- Handoffs entre departamentos
- Comunicación de políticas

#### Beneficios de Vista de Pájaro

✅ **Rápido de entender** - Mensaje claro y directo
✅ **Enfoque en valor** - Solo lo que importa al negocio
✅ **Comunicación efectiva** - Todos entienden
✅ **Decisiones estratégicas** - Sin perderse en detalles
✅ **Tiempo eficiente** - Menos tiempo de explicación

#### Riesgos de Vista de Pájaro

⚠️ **Falta de contexto** - Puede perder matices
⚠️ **Implementación difícil** - No hay suficiente detalle
⚠️ **Asunciones implícitas** - Se asume conocimiento
⚠️ **No apto para desarrollo** - Falta especificidad

---

### Cuándo Usar Vista de Mar/Peces (Fine-Grained)

#### Escenarios Apropiados

**1. Desarrollo de Software**
- Especificaciones técnicas
- Documentación de API
- Testing y QA
- Integración de sistemas

**Ejemplo:**
```
Desarrollador: "¿Cómo funciona el login?"
Tú: "Ok, necesitas ver el detalle: el usuario ingresa email, sistema valida formato, verifica en DB..."
```

**2. Automatización de Procesos**
- Diseño de workflows
- RPA (Robotic Process Automation)
- Optimización operativa
- Eliminación de tareas manuales

**Ejemplo:**
```
Analista: "¿Qué tareas son automáticas?"
Tú: "En detalle: pasos 1-3 son automáticos, paso 4 requiere intervención manual..."
```

**3. Resolución de Problemas**
- Root cause analysis
- Mejora de procesos ineficientes
- Auditoría de cumplimiento
- Troubleshooting

**Ejemplo:**
```
"Why is this taking so long?"
Tú: "En el paso 7, hay 3 validaciones manuales que toman 15 minutos cada una..."
```

**4. Training Operativo**
- Manuales de usuario
- Documentación de procedimientos
- Capacitación específica
- Onboarding detallado

**Ejemplo:**
```
Entrenamiento: "¿Cómo hago la factura?"
Tú: "Paso a paso: abres sistema, buscas orden, completas campos..."
```

#### Beneficios de Vista de Mar/Peces

✅ **Implementación clara** - Especificación completa
✅ **Identifica problemas** - Ve ineficiencias específicas
✅ **Automatización posible** - Detalle para RPA
✅ **Training efectivo** - Procedimientos claros
✅ **Testing exhaustivo** - Cada paso se puede probar

#### Riesgos de Vista de Mar/Peces

⚠️ **Overwhelming** - Demasiado detalle
⚠️ **Tiempo-consuming** - Toma más tiempo capturar
⚠️ **Perderse en detalles** - Puede perder vista general
⚠️ **Cambios difíciles** - Más rígido

---

## Metodología para Determinar Granularidad

### Preguntas para Definir Nivel Apropiado

#### 1. Pregunta por el Propósito

**Tú:** "¿Para qué vamos a usar este modelo?"

| Propósito | Granularidad Recomendada |
|-----------|--------------------------|
| **Presentación ejecutiva** | Coarse (Pájaro) |
| **Desarrollo de sistema** | Fine (Mar/Peces) |
| **Identificar problemas** | Fine (Mar/Peces) |
| **Comunicación general** | Coarse (Pájaro) |
| **Automatización** | Fine (Mar/Peces) |
| **Training de alto nivel** | Coarse (Pájaro) |
| **Manual operativo** | Fine (Mar/Peces) |

#### 2. Pregunta por la Audiencia

**Tú:** "¿Quién va a usar/ver este modelo?"

| Audiencia | Conocimiento Técnico | Granularidad Recomendada |
|-----------|---------------------|--------------------------|
| **Ejecutivos** | Bajo | Coarse (Pájaro) |
| **Desarrolladores** | Alto | Fine (Mar/Peces) |
| **Usuarios finales** | Medio | Fine para su área |
| **Stakeholders** | Variable | Coarse (Pájaro) |
| **Auditores** | Medio | Fine (Mar/Peces) |
| **Clientes** | Bajo | Coarse (Pájaro) |

#### 3. Pregunta por el Contexto de Uso

**Tú:** "¿En qué contexto se va a usar?"

| Contexto | Ejemplo | Granularidad |
|----------|---------|--------------|
| **Decisión estratégica** | "¿Invertimos en esto?" | Coarse |
| **Estimación desarrollo** | "¿Cuánto cuesta hacer X?" | Fine |
| **Comunicación** | "Explicar a cliente" | Coarse |
| **Implementación** | "Desarrollar feature" | Fine |
| **Análisis** | "¿Dónde es lento?" | Fine |
| **Visión general** | "Entender negocio" | Coarse |

### Matriz de Decisión

| Audiencia \ Propósito | Presentar | Desarrollar | Problemas | Decidir |
|-----------------------|-----------|-------------|-----------|---------|
| **Ejecutivos** | Coarse | - | - | Coarse |
| **Desarrolladores** | Fine | Fine | Fine | Fine |
| **Usuarios** | Coarse | Fine | Fine | - |
| **Stakeholders** | Coarse | - | - | Coarse |

---

## Técnicas para Ajustar Granularidad

### De Coarse a Fine (Zoom In)

#### Señales de que Necesitas Más Detalle

- Preguntas sobre implementación: "¿Cómo funciona X?"
- Dudas sobre pasos específicos: "¿Y después qué pasa?"
- Necesidad de automatizar: "Queremos automatizar esto"
- Identificar problemas: "¿Por qué es lento?"

#### Frases de Transición

**Tú:** "Para [propósito], necesitamos más detalle. ¿Podemos profundizar en [área]?"

**Ejemplo:**
"Para poder automatizar el paso 3, necesitamos saber qué validaciones hace exactamente. ¿Podemos ver en detalle cómo funciona?"

#### Proceso de Zoom In

**1. Identifica el área a profundizar**
```
Ejemplo: Paso 3 "Operaciones ejecuta servicio"
```

**2. Divide en sub-pasos**
```
3.1. `Técnico recibe orden`
3.2. `Técnico verifica herramientas`
3.3. `Técnico se desplaza`
3.4. `Técnico realiza diagnóstico`
3.5. `Técnico completa reparación`
3.6. `Técnico verifica funcionamiento`
3.7. `Técnico documenta trabajo`
3.8. `Técnico solicita firma cliente`
3.9. `Técnico sube documentación`
```

**3. Aplica mismo proceso recursivamente si necesario**
```
3.4. `Técnico realiza diagnóstico`
3.4.1. `Técnico identifica problema`
3.4.2. `Técnico consulta manual si necesario`
3.4.3. `Técnico determina solución`
3.4.4. `Técnico verifica disponibilidad repuestos`
3.4.5. `Técnico decide proceder o reprogramar`
```

### De Fine a Coarse (Zoom Out)

#### Señales de que Tienes Demasiado Detalle

- Audiencia se pierde: "Esto es muy técnico"
- Tiempo excesivo: "Llevamos 2 horas en un paso"
- Pérdida de foco: "¿Cuál era el objetivo?"
- Resistencia del usuario: "No necesitamos tanto detalle"

#### Frases de Transición

**Tú:** "Para [audiencia/objetivo], una visión general será suficiente. ¿Te parece si resumimos a los pasos principales?"

**Ejemplo:**
"Para la presentación a dirección, no necesitamos ver cada validación. ¿Te parece si mantenemos los pasos a nivel de 'el sistema valida'?"

#### Proceso de Zoom Out

**1. Identifica pasos que se pueden agrupar**
```
Pasos actuales (too fine):
1.1. `Sistema valida formato email`
1.2. `Sistema verifica email no existe`
1.3. `Sistema guarda cliente en DB`
1.4. `Sistema envía email bienvenida`

Se pueden agrupar:
1. `Cliente completa formulario web`
2. `Sistema valida y registra cliente` (agrupa 1.1-1.4)
```

**2. Encuentra el nivel apropiado**
```
Original: 20 pasos
Zoom out 1: 10 pasos (agrupar 2-3 pasos cada uno)
Zoom out 2: 5 pasos (agrupar 3-5 pasos cada uno)
```

**3. Verifica que la información crítica se mantiene**
```
¿Se pierde algún actor importante? No
¿Se pierde algún punto de decisión? No
¿Se pierde algún outcome? No
✅ Nivel apropiado encontrado
```

---

## Ejemplos por Dominio

### RRHH: Proceso de Contratación

#### Vista de Pájaro (Coarse-Grained)
```
Proceso de Contratación - Visión General

1. `Necesidad de Personal`
2. `Publicación de Oferta`
3. `Recepción de Candidaturas`
4. `Selección de Candidatos`
5. `Entrevistas`
6. `Selección Finalista`
7. `Contratación`
8. `Incorporación`

Duración: 4-6 semanas
Actores: RRHH, Recruiter, Candidatos
```

#### Vista de Mar/Peces (Fine-Grained)
```
Proceso de Contratación - Detalle Operativo

1. `Departamento identifica necesidad`
2. `Departamento completa formulario solicitud`
3. `Manager aprueba solicitud`
4. `RRHH recibe solicitud aprobada`
5. `RRHH crea descripción puesto`
6. `RRHH define criterios selección`
7. `RRHH publica en portal A`
8. `RRHH publica en portal B`
9. `RRHH contacta headhunters`
10. `Candidatos envían CVs`
11. `Sistema ATS registra aplicaciones`
12. `RRHH revisa CVs`
    12.1. `Verifica experiencia mínima`
    12.2. `Evalúa formación`
    12.3. `Revisa referencias`
    12.4. `Calcula score`
13. `RRHH preselecciona candidatos`
14. `RRHH programa entrevistas`
15. `Candidatos asisten a entrevistas`
16. `Entrevistadores evalúan candidatos`
17. `RRHH selecciona finalista`
18. `RRHH prepara oferta`
19. `RRHH negocia términos`
20. `Candidato acepta oferta`
21. `RRHH prepara contrato`
22. `Candidato firma contrato`
23. `RRHH programa onboarding`
24. `IT prepara equipos`
25. `RRHH programa formación`
26. `Empleado empieza`
...
```

---

### Ventas: Proceso de Presupuesto

#### Vista de Pájaro (Coarse-Grained)
```
Proceso de Presupuesto - Resumen Ejecutivo

1. `Cliente Solicita Presupuesto`
2. `Comercial Evalúa Requerimientos`
3. `Comercial Prepara Propuesta`
4. `Cliente Revisa Propuesta`
5. `Se Negocia si Necesario`
6. `Cliente Aprueba`
7. `Se Formaliza Contrato`

Duración: 1-2 semanas
```

#### Vista de Mar/Peces (Fine-Grained)
```
Proceso de Presupuesto - Detalle Técnico

1. `Cliente completa formulario web`
2. `Sistema valida datos cliente`
3. `Comercial recibe notificación`
4. `Comercial revisa solicitud`
5. `Comercial agenda llamada discovery`
6. `Comercial realiza llamada`
7. `Comercial identifica necesidades`
8. `Comercial evalúa viabilidad`
9. `Comercial consulta base precios`
10. `Comercial calcula costos`
11. `Comercial aplica descuentos`
12. `Comercial prepara propuesta`
13. `Comercial envía propuesta`
14. `Cliente recibe propuesta`
15. `Cliente revisa propuesta`
16. `Cliente solicita modificaciones`
17. `Comercial incorpora cambios`
18. `Comercial envía propuesta revisada`
19. `Cliente solicita reunión`
20. `Comercial agenda reunión`
21. `Comercial y cliente negocian`
22. `Cliente solicita descuento adicional`
23. `Comercial evalúa descuento`
24. `Comercial consulta políticas`
25. `Comercial decide aprobación/rechazo`
26. `Cliente acepta términos finales`
27. `Se prepara contrato`
28. `Cliente firma contrato`
...
```

---

### Operaciones: Proceso de Órdenes de Trabajo

#### Vista de Pájaro (Coarse-Grained)
```
Proceso de Órdenes - Visión General

1. `Cliente Solicita Servicio`
2. `Se Evalúa y Asigna`
3. `Técnico Ejecuta Servicio`
4. `Se Verifica Calidad`
5. `Se Factura al Cliente`
6. `Cliente Paga`

Duración: 1-5 días
```

#### Vista de Mar/Peces (Fine-Grained)
```
Proceso de Órdenes - Detalle Operativo

1. `Cliente llama o completa formulario`
2. `Recepcionista registra solicitud`
3. `Sistema crea orden preliminar`
4. `Comercial evalúa solicitud`
5. `Comercial verifica disponibilidad`
6. `Comercial prepara presupuesto`
7. `Cliente aprueba presupuesto`
8. `Sistema convierte a orden`
9. `Responsable asigna técnico`
10. `Técnico recibe orden`
11. `Técnico verifica herramientas`
12. `Técnico se desplaza`
13. `Técnico llega al lugar`
14. `Técnico realiza diagnóstico`
15. `Técnico identifica problema`
16. `Técnico verifica repuestos`
17. `Técnico realiza reparación`
18. `Técnico prueba funcionamiento`
19. `Técnico solicita firma conformidad`
20. `Cliente firma`
21. `Técnico completa parte trabajo`
22. `Técnico sube documentación`
23. `Sistema calcula costos`
24. `Administrativo genera factura`
25. `Factura se envía al cliente`
26. `Cliente recibe factura`
27. `Cliente paga factura`
...
```

---

## Errores Comunes con Granularidad

### Error 1: No Definir Granularidad al Inicio

❌ **Problema:**
```
Tú: "Cuéntame sobre el proceso de ventas"
Usuario: "Bien, cuando un cliente..."
[2 horas después]
Usuario: "¿Pero para qué necesitas saber si el email va a spam?"
```

✅ **Solución:**
```
Tú: "¿Para qué vamos a usar esto? ¿Es para una presentación o para desarrollar un sistema?"
Usuario: "Para desarrollar un CRM"
Tú: "Perfecto, entonces necesitamos ver en detalle cada paso para la implementación."
```

### Error 2: Mezclar Granularidades

❌ **Problema:**
```
1. `Cliente solicita servicio`
2. `Sistema valida email, verifica base de datos, guarda cliente, envía confirmación`
3. `Comercial evalúa`
```

**Problema:** Paso 2 es ultra-detallado, pasos 1 y 3 son muy generales.

✅ **Solución:**
```
Opción A (Coarse):
1. `Cliente solicita servicio`
2. `Sistema procesa solicitud`
3. `Comercial evalúa`

Opción B (Fine):
1.1. `Cliente completa formulario`
1.2. `Sistema valida email`
1.3. `Sistema verifica cliente`
1.4. `Sistema guarda datos`
2.1. `Comercial recibe notificación`
2.2. `Comercial revisa solicitud`
2.3. `Comercial decide`
```

### Error 3: Scope Creep Durante Sesión

❌ **Problema:**
```
Inicialmente: "Modelamos el proceso de aprobación"
[30 minutos después]
Usuario: "Y entonces el email va a spam, entonces tenemos que..."
Tú: "Sí, y ¿cómo detectamos que fue a spam?"
[2 horas después]
Usuario: "Esto se está complicando mucho..."
```

✅ **Solución:**
```
Tú: "Interrumpo un momento. Comenzamos modelando el proceso principal de aprobación. ¿Estás mencionando una variación o queremos cambiar a modelar también el manejo de errores?"
```

### Error 4: Persistir en Granularidad Inapropiada

❌ **Problema:**
```
Usuario: "Esto es muy técnico para nosotros"
Tú: "Pero necesitamos ver cada validación para..."
[Usuario se frustra, pierde interés]
```

✅ **Solución:**
```
Usuario: "Esto es muy técnico para nosotros"
Tú: "Tiene razón. ¿Le parece si hacemos una versión de visión general primero y luego, si necesitamos implementar, ahí profundizamos?"
```

### Error 5: No Comunicar Cambios de Granularidad

❌ **Problema:**
```
[Iniciaron coarse-grained]
[De repente tú cambias a fine sin avisar]
Usuario: "¿Por qué estamos viendo tantos detalles ahora?"
```

✅ **Solución:**
```
Tú: "Ahora que entendemos el flujo general, para poder automatizar el paso 3 necesitamos más detalle. ¿Podemos profundizar en esa parte?"
```

---

## Checklist para Granularidad Apropiada

### Antes de la Sesión

- [ ] ¿Definí el propósito del modelado?
- [ ] ¿Identifiqué la audiencia objetivo?
- [ ] ¿Clarifiqué el contexto de uso?
- [ ] ¿Elegí granularidad apropiada?
- [ ] ¿Comuniqué expectativas al usuario?

### Durante la Sesión

- [ ] ¿Mantengo el nivel de granularidad consistente?
- [ ] ¿La audiencia sigue el ritmo?
- [ ] ¿Estoy capturando el nivel de detalle necesario?
- [ ] ¿Evito scope creep?
- [ ] ¿Comunico cuando cambio granularidad?

### Después de la Sesión

- [ ] ¿El modelo sirve al propósito?
- [ ] ¿La audiencia puede usarlo?
- [ ] ¿Es el nivel de detalle apropiado?
- [ ] ¿Hay feedback sobre granularidad?
- [ ] ¿Necesito ajustar para futura sesión?

---

## Resumen: Granularidad

### Principios Clave

1. **Propósito determina granularidad** - No hay nivel "correcto" universal
2. **Audiencia importa** - Adapta al conocimiento y necesidad
3. **Consistencia es crucial** - Mantén mismo nivel en toda la historia
4. **Cambio es normal** - Adapta si es necesario
5. **Comunicación es clave** - Siempre clarifica el nivel

### Vista de Pájaro (Coarse-Grained)

**Cuándo usar:**
- Comunicación ejecutiva
- Visión general
- Presentaciones
- Decisiones estratégicas

**Características:**
- 5-15 pasos
- Actores principales
- Sin detalles técnicos
- Enfoque en valor

### Vista de Mar/Peces (Fine-Grained)

**Cuándo usar:**
- Desarrollo
- Automatización
- Resolución problemas
- Training detallado

**Características:**
- 20-100+ pasos
- Todos los actores
- Detalles técnicos
- Validaciones explícitas

### Frases Clave

**Para definir:**
- "¿Para qué vamos a usar esto?"
- "¿Quién va a leer esto?"
- "¿Necesitas visión general o detalle paso a paso?"

**Para cambiar:**
- "Para [propósito], necesitamos más/menos detalle"
- "¿Te parece si profundizamos/resumimos esta parte?"
- "Cambiamos de visión general a detalle porque..."

**Recuerda:** Ni más ni menos. El nivel apropiado es el que sirve al propósito. Mejor adaptar que forzar.
