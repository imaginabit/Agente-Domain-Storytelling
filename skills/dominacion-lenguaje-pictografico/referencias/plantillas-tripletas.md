# Plantillas para Tripletas Sujeto → Predicado → Objeto

Este documento proporciona plantillas reutilizables para estructurar información usando el formato de lenguaje pictográfico.

## Plantillas Básicas por Tipo de Actor

### Plantillas para Empleados/Personas

```
[Nombre del empleado/rol] → [verbo de acción] → [objeto de trabajo]
```

**Ejemplos:**
- `empleado → completa → orden de trabajo`
- `supervisor → aprueba → solicitud de vacaciones`
- `vendedor → genera → presupuesto`
- `técnico → realiza → reparación`
- `contable → registra → factura`

**Verbos comunes para personas:**
- ejecuta, realiza, completa, envía, recibe, revisa, aprueba, rechaza, actualiza, modifica, crea, elimina, archiva, procesa, valida, verifica, controla, registra, documenta, informa, comunica, coordina, supervisa, gestiona, administra, mantiene, repara, instala, configura, prueba, testa, valida, certifica

### Plantillas para Departamentos

```
[Departamento] → [verbo de acción] → [objeto de trabajo]
```

**Ejemplos:**
- `departamento de RRHH → procesa → nóminas`
- `departamento de IT → mantiene → servidores`
- `departamento de compras → gestiona → proveedores`
- `departamento de ventas → analiza → estadísticas`

**Verbos comunes para departamentos:**
- procesa, gestiona, coordina, supervisa, administra, mantiene, desarrolla, implementa, controla, revisa, actualiza, optimiza, evalúa, analiza, planifica, organiza, distribuye, asigna, consolida, integra

### Plantillas para Sistemas

```
[Sistema] → [verbo automático] → [objeto de trabajo]
```

**Ejemplos:**
- `sistema ERP → genera → informes automáticamente`
- `sistema CRM → registra → datos del cliente`
- `sistema de facturación → envía → facturas por email`
- `base de datos → almacena → información`

**Verbos comunes para sistemas:**
- genera, envía, registra, almacena, procesa, calcula, actualiza, sincroniza, backupea, integra, transforma, valida, verifica, notifica, alerta, muestra, calcula, ejecuta, automatiza, programara

### Plantillas para Entidades Externas

```
[Proveedor/Cliente/Entidad externa] → [verbo de acción] → [objeto de trabajo]
```

**Ejemplos:**
- `proveedor → entrega → materiales`
- `cliente → firma → contrato`
- `banco → transfiere → dinero`
- `consultora → realiza → auditoría`

## Plantillas por Objeto de Trabajo

### Plantillas para Documentos

```
[Actor] → [verbo sobre documento] → [tipo de documento]
```

**Ejemplos:**
- `empleado → completa → formulario`
- `departamento → genera → informe`
- `sistema → envía → factura`
- `cliente → firma → contrato`

**Verbos para documentos:**
- completa, genera, envía, recibe, firma, archiva, revisa, aprueba, rechaza, modifica, actualiza, valida, certifica, registra, procesa, gestiona, crea, edita, imprime, digitaliza

### Plantillas para Datos/Información

```
[Actor] → [verbo sobre datos] → [tipo de dato]
```

**Ejemplos:**
- `sistema → almacena → datos del cliente`
- `empleado → actualiza → información personal`
- `analista → procesa → datos de ventas`
- `sistema → genera → informe de estadísticas`

**Verbos para datos:**
- almacena, actualiza, procesa, analiza, genera, consulta, extrae, transforma, limpia, valida, verifica, sincroniza, exporta, importa, migra, consolida, calcula, computa

### Plantillas para Recursos Físicos

```
[Actor] → [verbo sobre recurso] → [tipo de recurso]
```

**Ejemplos:**
- `almacén → almacena → productos`
- `proveedor → entrega → materiales`
- `técnico → instala → equipos`
- `mantenimiento → repara → maquinaria`

**Verbos para recursos físicos:**
- almacena, entrega, instala, repara, mantiene, transporta, mueve, clasifica, etiqueta, embala, desembala, carga, descarga, inspecciona, verifica, controla, distribuye, asigna

## Plantillas por Actividad Empresarial

### Procesos de Aprobación

```
[Actor] → [solicita/aproba/rechaza] → [elemento a aprobar]
```

**Ejemplos:**
- `empleado → solicita → vacaciones`
- `supervisor → aprueba → solicitud de vacaciones`
- `departamento → rechaza → presupuesto`
- `responsable → autoriza → gasto extraordinario`

### Procesos de Comunicación

```
[Emisor] → [envía/comunica] → [Mensaje] → [a Receptor]
```

**Ejemplos:**
- `sistema → envía → notificación → a usuario`
- `departamento → comunica → cambios → a empleados`
- `cliente → presenta → reclamación → a soporte`
- `proveedor → notifica → retrasos → a compras`

### Procesos de Validación

```
[Validador] → [valida/verifica] → [elemento] → [contra criterio]
```

**Ejemplos:**
- `inspector → valida → producto → contra estándares de calidad`
- `sistema → verifica → datos → contra base de datos`
- `auditor → revisa → procesos → contra normativa`
- `supervisor → controla → cumplimiento → contra procedimientos`

### Procesos de Transformación

```
[Transformador] → [convierte/procesa] → [input] → [en output]
```

**Ejemplos:**
- `sistema → convierte → datos XML → en JSON`
- `departamento → procesa → solicitudes → en aprobaciones`
- `técnico → transforma → materia prima → en producto terminado`
- `sistema → consolida → datos → en informe`

## Plantillas Condicionales

### Condicionales con "Si... entonces..."

```
SI [condición], ENTONCES [actor] → [acción] → [objeto]
```

**Ejemplos:**
- `SI producto cumple estándares, ENTONCES sistema → etiqueta → como APROBADO`
- `SI factura > 1000€, ENTONCES director → aprueba → factura`
- `SI stock < mínimo, ENTONCES sistema → genera → orden de compra`

### Condicionales con "Cuando..."

```
CUANDO [evento], [actor] → [acción] → [objeto]
```

**Ejemplos:**
- `CUANDO cliente completa pedido, ENTONCES sistema → genera → factura`
- `CUANDO empleado solicita vacaciones, ENTONCES supervisor → revisa → solicitud`
- `CUANDO se detecta fallo, ENTONCES sistema → alerta → a administrador`

## Plantillas por Dominio Empresarial

### RRHH (Recursos Humanos)

```
[Actores RRHH] → [acción] → [elementos RRHH]
```

**Actores:** empleado, supervisor, RRHH, recruiter, responsable de nóminas, director
**Objetos:** empleado, contrato, nómina, vacaciones, formación, evaluación, candidato, puesto
**Actividades:** contrata, forma, evalúa, promociona, despide, paga, registra, asigna, programa

**Ejemplos:**
- `RRHH → contrata → nuevo empleado`
- `responsable → evalua → rendimiento`
- `departamento → paga → nóminas`
- `empleado → solicita → vacaciones`

### Operaciones/Producción

```
[Actores de producción] → [acción] → [elementos de producción]
```

**Actores:** operario, supervisor de producción, técnico, mantenimiento, calidad, logística
**Objetos:** producto, orden de producción, maquinaria, materia prima, producto terminado, defecto
**Actividades:** fabrica, ensambla, controla, mantiene, repara, inspecciona, embala, envía

**Ejemplos:**
- `operario → fabrica → producto`
- `mantenimiento → repara → maquinaria`
- `calidad → inspecciona → productos`
- `logística → envía → productos terminados`

### Ventas/Comercial

```
[Actores comerciales] → [acción] → [elementos comerciales]
```

**Actores:** vendedor, comercial, director de ventas, cliente, prospect
**Objetos:** presupuesto, pedido, cliente, producto, comisión, lead, oportunidad
**Actividades:** vende, negocia, cierra, presenta, visita, contacta, sigue, reporta

**Ejemplos:**
- `vendedor → negocia → presupuesto`
- `comercial → contacta → prospect`
- `director → analiza → ventas`
- `cliente → firma → pedido`

### Finanzas/Contabilidad

```
[Actores financieros] → [acción] → [elementos financieros]
```

**Actores:** contable, controller, director financiero, banco, auditor
**Objetos:** factura, pago, saldo, presupuesto, inversión, coste, ingreso, análisis
**Actividades:** contabiliza, paga, cobra, analiza, controla, audita, planifica, invierte

**Ejemplos:**
- `contable → contabiliza → factura`
- `controller → analiza → costes`
- `banco → transfiere → fondos`
- `director → planifica → presupuesto`

## Validación de Tripletas

### Checklist de Validación

**Para cada tripleta, verifica:**
- [ ] ¿El actor puede realizar la acción?
- [ ] ¿La acción es apropiada para el objeto?
- [ ] ¿La tripleta tiene sentido completo?
- [ ] ¿Se usa terminología consistente?
- [ ] ¿Hay redundancias o elementos faltantes?

### Patrones de Errores Comunes

**❌ Error: Actor no puede realizar la acción**
- `mesa → envía → email` (incorrecto)
- `empleado → envía → email` (correcto)

**❌ Error: Acción no apropiada para el objeto**
- `empleado → come → datos` (incorrecto)
- `empleado → procesa → datos` (correcto)

**❌ Error: Tripleta incompleta**
- `empleado completa` (incorrecto - falta objeto)
- `empleado → completa → formulario` (correcto)

**❌ Error: Múltiples objetos en una tripleta**
- `empleado → completa → formulario y lo envía` (incorrecto)
- `empleado → completa → formulario`
- `empleado → envía → formulario` (correcto)