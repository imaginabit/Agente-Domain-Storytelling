# Audiencias y Scope

Este documento explica cómo adaptar el nivel de granularidad y perspectiva (As-Is/To-Be) según la audiencia objetivo, considerando su conocimiento técnico, necesidades específicas y contexto de uso para asegurar que el modelado sea apropiado y efectivo.

## Principios de Adaptación a Audiencia

### Regla Fundamental
**"El mismo proceso, diferentes niveles de detalle según quién lo vea"**

No existe un nivel "correcto" universal. El scope apropiado depende de:
- **Quién** lo va a usar (audiencia)
- **Para qué** lo va a usar (propósito)
- **Cuándo** lo va a usar (momento del proyecto)

---

## Matriz de Audiencias

### Audiencia 1: Ejecutivos/Directivos

#### Características
- **Conocimiento técnico:** Bajo
- **Tiempo disponible:** Limitado
- **Enfoque:** Resultados de negocio, ROI, visión estratégica
- **Decisiones:** Aprobación de presupuesto, dirección estratégica

#### Scope Recomendado

**Granularidad:** Coarse-Grained (Pájaro/Cometa)
- 5-10 pasos máximo
- Visión general sin detalles técnicos
- Enfoque en outcomes y valor

**Perspectiva:** Híbrido (As-Is + To-Be)
- Mostrar estado actual (problema)
- Mostrar estado futuro (solución)
- Enfatizar gap y beneficios

**Formato Sugerido:**
```
Proceso de [X] - Resumen Ejecutivo

AS-IS (Estado Actual):
- Problema principal
- Costo/Impacto actual
- Pain points críticos

TO-BE (Estado Futuro):
- Beneficios esperados
- ROI proyectado
- Timeline de implementación

DECISIÓN REQUERIDA:
[Aprobación/Inversión/Recursos]
```

#### Ejemplo: Presentación a CEO

```
Digitalización RRHH - Presentación Ejecutiva

AS-IS (Problema Actual):
1. `Empleados solicitan vacaciones` → 3-5 días proceso
2. `Múltiples formularios papel` → Ineficiente
3. `Verificación manual errores` → 15% error rate
4. `Actualización Excel inconsistente` → Datos incorrectos

COSTO ACTUAL: €81,600/año en ineficiencias

TO-BE (Solución Futura):
1. `Portal self-service` → 2 horas proceso
2. `Automatización 90%` → Sin errores
3. `Integración sistemas` → Datos consistentes

AHORRO PROYECTADO: €74,400/año (91% reducción)
ROI: 312% en 3 años
PAYBACK: 4 meses

DECISIÓN REQUERIDA:
Inversión: €25,000
Aprobación: ¿Procedemos?
```

#### Preguntas para Ejecutivos

- "¿Cuál es el impacto en el negocio?"
- "¿Cuánto cuesta no hacer nada?"
- "¿Cuál es el ROI esperado?"
- "¿Qué riesgo hay si no cambiamos?"
- "¿Cuánto tiempo toma ver resultados?"

---

### Audiencia 2: Desarrolladores/Técnicos

#### Características
- **Conocimiento técnico:** Alto
- **Tiempo disponible:** Generoso para detalles
- **Enfoque:** Implementación, arquitectura, especificaciones
- **Decisiones:** Diseño técnico, estimación de esfuerzo

#### Scope Recomendado

**Granularidad:** Fine-Grained (Mar/Peces)
- 50-100+ pasos
- Cada validación y excepción
- Sistemas y APIs mencionados
- Detalles de implementación

**Perspectiva:** To-Be (Proceso Futuro)
- Proceso optimizado para implementar
- Sin problemas actuales
- Automatización máxima
- Especificaciones técnicas

**Formato Sugerido:**
```
Sistema de [X] - Especificación Técnica

PROCESO OPTIMIZADO:
1. [Paso detallado]
   1.1. [Sub-paso]
   1.2. [Validación]
   1.3. [Excepción]

ARQUITECTURA:
- Frontend: [Tecnología]
- Backend: [Tecnología]
- Base de datos: [Tipo]
- APIs: [Endpoints]

INTEGRACIONES:
- [Sistema A]: [Método]
- [Sistema B]: [Método]

AUTOMATIZACIÓN:
- Paso 1-3: Automático
- Paso 4: Manual (requiere intervención)
```

#### Ejemplo: Workshop con Desarrolladores

```
Sistema de Vacaciones - Especificación Técnica

PROCESO OPTIMIZADO:

1. `Frontend: Empleado accede portal`
   1.1. `Autenticación JWT`
   1.2. `Carga datos empleado desde API`
   1.3. `Renderiza calendario interactivo`

2. `Frontend: Empleado selecciona fechas`
   2.1. `Validación cliente: max 22 días`
   2.2. `Validación cliente: no superposición`
   2.3. `Cálculo días en tiempo real`

3. `Frontend: Empleado envía solicitud`
   3.1. `POST /api/vacation/request`
   3.2. `Payload: {empleadoId, fechas, comentario}`
   3.3. `Validación servidor`

4. `Backend: Procesar solicitud`
   4.1. `Verificar días disponibles (DB query)`
   4.2. `Verificar conflictos (DB query)`
   4.3. `Guardar solicitud (DB insert)`
   4.4. `Generar solicitud ID`

5. `Backend: Notificar supervisor`
   5.1. `Buscar supervisor empleado (DB query)`
   5.2. `Enviar email (queue: notification_queue)`
   5.3. `Enviar push notification`

6. `Frontend: Supervisor aprueba`
   6.1. `PUT /api/vacation/{id}/approve`
   6.2. `Validar permisos supervisor`
   6.3. `Actualizar status (DB update)`

7. `Backend: Finalizar proceso`
   7.1. `Actualizar calendario empleado (DB update)`
   7.2. `Sincronizar con nóminas (API call)`
   7.3. `Enviar confirmación empleado (email + push)`

ARQUITECTURA:
- Frontend: Vue.js + TypeScript
- Backend: Laravel 8 + PHP
- Base de datos: MySQL 8.0
- Queue: Redis + Horizon
- Notificaciones: Pusher + SendGrid

APIs:
- GET /api/vacation/available/{empleadoId}
- POST /api/vacation/request
- PUT /api/vacation/{id}/approve
- GET /api/vacation/calendar/{empleadoId}
```

#### Preguntas para Desarrolladores

- "¿Qué sistemas necesitan integrarse?"
- "¿Cuáles son las validaciones específicas?"
- "¿Qué excepciones deben manejarse?"
- "¿Cuál es el volumen esperado?"
- "¿Qué nivel de concurrencia debe soportar?"

---

### Audiencia 3: Usuarios Finales/Operativos

#### Características
- **Conocimiento técnico:** Medio
- **Tiempo disponible:** Para aprender su proceso
- **Enfoque:** Su trabajo diario, tareas específicas
- **Decisiones:** Cómo hacer su trabajo mejor

#### Scope Recomendado

**Granularidad:** Fine-Grained (para su área específica)
- Pasos específicos de su rol
- Sin detalles técnicos de otros sistemas
- Ejemplos concretos con datos reales
- Screenshots/prototipos si es posible

**Perspectiva:** As-Is (Proceso Actual) + To-Be (Mejoras)
- Primero entender cómo funciona ahora
- Luego mostrar mejoras en su área
- Focus en beneficios para ellos

**Formato Sugerido:**
```
Proceso de [X] - Guía para [Rol]

TU TRABAJO ACTUAL:
1. [Paso que haces]
   - Dónde: [Ubicación/Sistema]
   - Cuándo: [Frecuencia]
   - Problema: [Si aplica]

TU TRABAJO FUTURO:
1. [Paso mejorado]
   - Beneficio: [Qué gana]
   - Cambios: [Qué es diferente]

EJEMPLO REAL:
[Escenario concreto con datos]
```

#### Ejemplo: Sesión con María (Administrativa)

```
Proceso de Facturación - Guía para María

TU TRABAJO ACTUAL:
1. `Recibir partes de trabajo`
   - Dónde: Bandeja de entrada físico
   - Cuándo: Cuando técnico trae
   - Problema: Se mezclan con otros documentos

2. `Buscar orden en sistema`
   - Dónde: Sistema facturación
   - Cómo: Por número de orden
   - Problema: A veces número no coincide

3. `Introducir datos manualmente`
   - Dónde: Formulario sistema
   - Campos: Cliente, horas, materiales
   - Problema: Tedioso, errores frecuentes

4. `Calcular precios`
   - Dónde: Calculadora + tabla tarifas
   - Problema: Errores de cálculo, 15% tasa error

5. `Generar y enviar factura`
   - Dónde: Sistema + Outlook
   - Problema: PDF a veces no genera bien

TU TRABAJO FUTURO:
1. `Dashboard muestra órdenes completadas`
   - Beneficio: No buscar, aparece solo
   - Cambio: Ve orden automáticamente

2. `Datos vienen pre-cargados`
   - Beneficio: Solo verificar, no escribir
   - Cambio: Sistema copia desde tablet técnico

3. `Precios calculados automáticamente`
   - Beneficio: Sin cálculos manuales
   - Cambio: Sistema calcula todo

4. `Factura automática`
   - Beneficio: Un clic para enviar
   - Cambio: Sin generar PDF manual

EJEMPLO REAL:
Orden #12345 - Cliente ABC Corp
- Horas: 8 (pre-cargado desde tablet)
- Materiales: €150 (pre-cargado)
- Precio: €800 (calculado automáticamente)
- [María solo verifica y hace clic "Enviar"]
```

#### Preguntas para Usuarios Finales

- "¿Cómo haces esto hoy?"
- "¿Qué parte es más tediosa?"
- "¿Qué errores sueles cometer?"
- "¿Qué te gustaría que fuera más fácil?"
- "¿Qué información necesitas para hacer tu trabajo?"

---

### Audiencia 4: Stakeholders/Clientes

#### Características
- **Conocimiento técnico:** Variable (generalmente bajo)
- **Tiempo disponible:** Interesados pero no expertos
- **Enfoque:** Impacto en ellos, cambios que notarán
- **Decisiones:** Aprobación, feedback, adopción

#### Scope Recomendado

**Granularidad:** Coarse-Grained (Pájaro/Cometa)
- Visión general del proceso
- Qué cambia para ellos
- Beneficios que percibirán
- Timeline de cambios

**Perspectiva:** To-Be (Proceso Futuro)
- Proceso mejorado que experimentarán
- Sin detalles de implementación
- Focus en experiencia de usuario

**Formato Sugerido:**
```
Mejoras en [Proceso] - Lo que Cambia para Ti

PROCESO ACTUAL:
1. [Situación actual que conocen]

PROCESO MEJORADO:
1. [Nueva experiencia]

BENEFICIOS PARA TI:
- [Beneficio 1]
- [Beneficio 2]
- [Beneficio 3]

TIMELINE:
- [Fecha]: Implementación
- [Fecha]: Disponibilidad para ti
```

#### Ejemplo: Comunicación a Clientes

```
Nuevo Sistema de Órdenes - Lo que Cambia para Ti

PROCESO ACTUAL (Como funciona ahora):
1. `Llamas para solicitar servicio`
2. `Te llamamos para confirmar presupuesto`
3. `Vienes a oficina para firmar`
4. `Técnico hace el trabajo`
5. `Vienes a recoger factura`

PROCESO MEJORADO (Nueva experiencia):
1. `Solicitas via web (24/7)`
2. `Recibes presupuesto automático por email`
3. `Firmas digitalmente desde casa`
4. `Tracking en tiempo real del técnico`
5. `Recibes factura digital automáticamente`

BENEFICIOS PARA TI:
- ✅ Disponibilidad 24/7 (no esperas horario oficina)
- ✅ Respuesta más rápida (presupuesto en minutos)
- ✅ Sin viajes (todo digital)
- ✅ Tracking en tiempo real (sabes dónde está el técnico)
- ✅ Factura inmediata (sin esperas)

TIMELINE:
- Enero 2025: Lanzamiento nuevo sistema
- Enero 2025: Disponible para ti
- Soporte: Te ayudamos en la transición

¿Preguntas? Responde este email o llama al 900-XXX-XXX
```

#### Preguntas para Stakeholders

- "¿Qué cambios notarán?"
- "¿Será más fácil o más complicado?"
- "¿Cuándo estará disponible?"
- "¿Qué soporte tendrán?"
- "¿Hay riesgos para ellos?"

---

### Audiencia 5: Auditores/Compliance

#### Características
- **Conocimiento técnico:** Medio-Alto
- **Tiempo disponible:** Para revisar en detalle
- **Enfoque:** Cumplimiento, trazabilidad, controles
- **Decisiones:** Aprobación, recomendaciones

#### Scope Recomendado

**Granularidad:** Fine-Grained (Mar/Peces)
- Cada paso documentado
- Controles y validaciones
- Trazabilidad completa
- Evidencias y registros

**Perspectiva:** As-Is (Estado Actual) + To-Be (Estado Futuro)
- Documentar controles actuales
- Proponer controles mejorados
- Mostrar compliance gap

**Formato Sugerido:**
```
Proceso de [X] - Revisión Compliance

CONTROLES ACTUALES:
1. [Paso] - Control: [Qué se controla]
   - Responsable: [Quién]
   - Evidencia: [Qué se guarda]
   - Gap: [Si aplica]

CONTROLES PROPUESTOS:
1. [Paso mejorado] - Control: [Nuevo control]
   - Responsable: [Quién/Sistema]
   - Evidencia: [Qué se guarda]
   - Mejora: [Qué mejora]
```

#### Pregunta para Auditores

- "¿Qué controles existen actualmente?"
- "¿Qué evidencia se mantiene?"
- "¿Dónde están los gaps de compliance?"
- "¿Qué riesgos identifican?"
- "¿Qué recomiendan mejorar?"

---

## Adaptación Dinámica Durante Sesión

### Situación 1: Audiencia Mixta

**Escenario:** Sesión con equipo mixto (técnicos + negocio)

**Estrategia:**
1. **Empezar coarse-grained** (visión general para todos)
2. **Profundizar selectivamente** según tema
3. **Traducir entre mundos** (técnico ↔ negocio)

**Ejemplo:**
```
Tú (empezando): "Empecemos con visión general del proceso"

[Modelo coarse-grained completado]

Desarrollador: "Necesitamos más detalle en la integración con CRM"
Tú: "Perfecto, para esa parte específica, profundicemos. [Cambia a fine-grained para integración]"
[Profundiza solo esa parte]

Negocio: "Eso está muy técnico"
Tú: "Tiene razón, resumamos. Para el resto del proceso, mantenemos visión general"
[Regresa a coarse-grained]
```

### Situación 2: Audiencia No Técnica Pide Detalle

**Escenario:** Ejecutivo pregunta "¿cómo funciona exactamente?"

**Respuesta Estratégica:**
```
Opción A: Ofrecer dos niveles
"Podemos hacerlo de dos maneras:
1. Visión general (2 minutos) - para entender el concepto
2. Detalle técnico (30 minutos) - para implementación

¿Qué prefieres?"

Opción B: Enfocar en "qué" no "cómo"
"Para entender el impacto, no necesitamos el cómo técnico. ¿Le interesa más el qué cambia o el cómo funciona internamente?"
```

### Situación 3: Audiencia Técnica Pide Visión General

**Escenario:** Desarrollador dice "esto es demasiado detalle"

**Respuesta Estratégica:**
```
"Entendido. ¿Le parece si hacemos dos versiones:
1. Esta versión detallada (para implementación)
2. Una versión resumida (para presentación a dirección)

¿Cuál hacemos primero?"
```

---

## Plantillas por Audiencia

### Template para Ejecutivos

```
[Proceso] - Resumen Ejecutivo

SITUACIÓN ACTUAL (AS-IS):
- Problema: [Descripción problema principal]
- Impacto: [Costo/Tiempo/Errores]
- Frecuencia: [Cuándo ocurre]

PROPUESTA (TO-BE):
- Solución: [Descripción mejora]
- Beneficios: [Lista de beneficios]
- Inversión: [Costo estimado]
- ROI: [Retorno esperado]

DECISIÓN REQUERIDA:
- [Decisión específica]
- [Timeline]
- [Próximos pasos]
```

### Template para Desarrolladores

```
[Sistema] - Especificación Técnica

ARQUITECTURA:
- Frontend: [Tecnologías]
- Backend: [Tecnologías]
- Base de datos: [Tipo]
- Integraciones: [Lista]

FLUJO DETALLADO:
[Numerado con sub-pasos]

APIs:
[Lista de endpoints]

EXCEPCIONES:
[Lista de casos especiales]

CONSIDERACIONES:
- Performance: [Volumen esperado]
- Seguridad: [Controles]
- Escalabilidad: [Crecimiento]
```

### Template para Usuarios Finales

```
[Proceso] - Tu Nueva Forma de Trabajar

ANTES (Tu trabajo actual):
1. [Paso actual]
   - Dónde: [Sistema/Ubicación]
   - Problema: [Si aplica]

AHORA (Tu trabajo mejorado):
1. [Paso mejorado]
   - Beneficio: [Qué ganas]
   - Cambio: [Qué es diferente]

EJEMPLO:
[Escenario concreto]

TUS BENEFICIOS:
- [Beneficio 1]
- [Beneficio 2]
- [Beneficio 3]
```

---

## Errores Comunes con Audiencias

### Error 1: Un Nivel para Todos

❌ **Problema:**
```
Mismo nivel de detalle para CEO y desarrollador
```

✅ **Solución:**
```
CEO: 5 pasos, visión general, ROI
Desarrollador: 50 pasos, detalle técnico, APIs
```

### Error 2: No Adaptar Lenguaje

❌ **Problema:**
```
"Implementamos un endpoint REST que hace POST a /api/vacation"
[Para CEO]
```

✅ **Solución:**
```
"El empleado envía su solicitud y el sistema la procesa automáticamente"
[Para CEO]
```

### Error 3: Asumir Conocimiento

❌ **Problema:**
```
"Como sabemos, la validación de negocio se hace en el middleware"
[Sin explicar qué es middleware]
```

✅ **Solución:**
```
"Antes de guardar la solicitud, el sistema verifica que todo está correcto"
[Explica conceptos]
```

### Error 4: No Validar Entendimiento

❌ **Problema:**
```
Presentar modelo complejo sin verificar comprensión
```

✅ **Solución:**
```
"¿Esto refleja lo que necesita saber? ¿Falta algo importante?"
```

---

## Checklist por Audiencia

### Para Ejecutivos

- [ ] ¿Está claro el impacto de negocio?
- [ ] ¿Se muestra el ROI?
- [ ] ¿Se explica por qué importa?
- [ ] ¿Es conciso (5-10 minutos lectura)?
- [ ] ¿Hay una decisión clara que tomar?

### Para Desarrolladores

- [ ] ¿Hay suficiente detalle técnico?
- [ ] ¿Se especifican integraciones?
- [ ] ¿Se manejan excepciones?
- [ ] ¿Se consideran constraints técnicos?
- [ ] ¿Es implementable?

### Para Usuarios Finales

- [ ] ¿Se enfoca en su trabajo específico?
- [ ] ¿Se muestran beneficios claros?
- [ ] ¿Hay ejemplos concretos?
- [ ] ¿Es fácil de entender?
- [ ] ¿Se explica qué cambia para ellos?

### Para Stakeholders

- [ ] ¿Se explica qué cambios notarán?
- [ ] ¿Se minimiza la fricción?
- [ ] ¿Se muestra timeline claro?
- [ ] ¿Se ofrece soporte?
- [ ] ¿Se addressed concerns?

---

## Resumen: Audiencias y Scope

### Principios Clave

1. **Audiencia determina scope** - No hay nivel universal
2. **Propósito guía granularidad** - Detalle apropiado para uso
3. **Adapta lenguaje** - Técnico vs. negocio
4. **Valida entendimiento** - Asegúrate que sirve
5. **Sé flexible** - Cambia según feedback

### Matriz Rápida

| Audiencia | Granularidad | Perspectiva | Enfoque |
|-----------|--------------|-------------|---------|
| **Ejecutivos** | Coarse | Híbrido | ROI/Business |
| **Desarrolladores** | Fine | To-Be | Implementación |
| **Usuarios** | Fine (su área) | As-Is + To-Be | Beneficios |
| **Stakeholders** | Coarse | To-Be | Experiencia |
| **Auditores** | Fine | Híbrido | Compliance |

### Frases Clave

**Para definir audiencia:**
- "¿Quién va a usar esto?"
- "¿Para qué lo necesitan?"
- "¿Qué decisión van a tomar?"

**Para adaptar scope:**
- "Para [audiencia], necesitamos [nivel] detalle"
- "¿Le parece si resumimos/profundizamos esta parte?"
- "Para [propósito], esto es suficiente/demasiado"

**Recuerda:** El mejor modelo es el que sirve a la audiencia. Adapta, no impongas.
