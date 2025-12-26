# Assets - Iconos SVG para Lenguaje Pictográfico

Este directorio contiene los iconos SVG utilizados para visualizar actores y objetos de trabajo en diagramas de lenguaje pictográfico.

## Estructura de Directorios

```
assets/
├── actores/          # Iconos de actores (personas, grupos, sistemas)
└── objetos/          # Iconos de objetos de trabajo (documentos, etc.)
```

## Iconos de Actores

### 👤 Person (Persona Individual)
**Archivo:** `actores/person.svg`

Representa personas individuales:
- Empleados específicos
- Clientes individuales
- Técnicos
- Vendedores
- Supervisores individuales
- Usuarios finales

### 👥 Group (Grupo o Equipo)
**Archivo:** `actores/group.svg`

Representa grupos o equipos:
- Departamentos
- Equipos de trabajo
- Comités
- Grupos de empleados
- Unidades organizacionales
- Stakeholders múltiples

### 💻 System (Sistema Automatizado)
**Archivo:** `actores/system.svg`

Representa sistemas automatizados:
- Software (ERP, CRM, etc.)
- Bases de datos
- Aplicaciones
- Plataformas automatizadas
- APIs
- Herramientas tecnológicas

## Iconos de Objetos de Trabajo

### 📄 Document (Documentos)
**Archivo:** `objetos/document.svg`

Representa documentos:
- Facturas
- Contratos
- Informes
- Certificados
- Presupuestos
- Propuestas
- Actas

### 📁 Folder (Archivos/Carpetas)
**Archivo:** `objetos/folder.svg`

Representa archivos y carpetas:
- Expedientes
- Carpetas de proyecto
- Archivos múltiples
- Registros históricos
- Bases de conocimiento
- Documentación

### 📞 Call (Comunicaciones - Llamadas)
**Archivo:** `objetos/call.svg`

Representa comunicaciones:
- Llamadas telefónicas
- Videollamadas
- Conferencias
- Contactos directos
- Comunicación en vivo

### ✉️ Email (Emails y Notificaciones)
**Archivo:** `objetos/email.svg`

Representa emails y notificaciones:
- Emails de notificación
- Mensajes automáticos
- Newsletters
- Alertas del sistema
- Comunicaciones formales

### 📝 Form (Formularios y Solicitudes)
**Archivo:** `objetos/form.svg`

Representa formularios:
- Solicitudes de vacaciones
- Formularios de registro
- Solicitudes de compra
- Formularios de evaluación
- Peticiones de cambio
- Formularios de contacto

### 🗄️ Database (Bases de Datos y Registros)
**Archivo:** `objetos/database.svg`

Representa bases de datos:
- Registros de clientes
- Datos históricos
- Catálogos de productos
- Inventarios
- Bases de conocimiento
- Repositorios de datos

### 📊 Report (Reportes y Análisis)
**Archivo:** `objetos/report.svg`

Representa reportes:
- Reportes de ventas
- Informes de rendimiento
- Análisis de datos
- Dashboard
- Métricas y KPIs
- Estudios de mercado

### 💰 Money (Transacciones Financieras)
**Archivo:** `objetos/money.svg`

Representa transacciones financieras:
- Pagos
- Cobros
- Transferencias
- Facturas
- Presupuestos
- Inversiones

### 🛒 Cart (Pedidos y Compras)
**Archivo:** `objetos/cart.svg`

Representa pedidos y compras:
- Órdenes de compra
- Pedidos de clientes
- Cestas de compras
- Solicitudes de materiales
- Requerimientos de inventario

### 📅 Calendar (Eventos y Programación)
**Archivo:** `objetos/calendar.svg`

Representa eventos y programación:
- Calendarios de vacaciones
- Programación de citas
- Agenda de reuniones
- Cronogramas
- Plazos
- Recordatorios

## Cómo Usar los Iconos

### En HTML/Markdown
```html
<img src="assets/actores/person.svg" alt="Persona" width="24" height="24">
<img src="assets/objetos/document.svg" alt="Documento" width="24" height="24">
```

### En Documentación
```markdown
👤 [Empleado] → 📄 [Formulario]
```
(Los emojis son equivalentes visuales de los SVG)

### Estilos Personalizados
Los iconos usan `stroke="currentColor"`, lo que significa que heredan el color del texto padre:

```css
.icon-container {
  color: #333;
}

.icon-container img {
  width: 24px;
  height: 24px;
}
```

## Beneficios de Usar SVG

✅ **Escalables** - Se ven bien en cualquier tamaño
✅ **Personalizables** - Color, tamaño y estilo adaptables
✅ **Ligeros** - Tamaño de archivo mínimo
✅ **Accesibles** - Soporte completo para lectores de pantalla
✅ **Consistentes** - Apariencia uniforme en todos los navegadores

## Integración con Diagramas

Los iconos están diseñados para funcionar con el formato de tripletas:
```
[Actor Icon] [Actor] → [Actividad] → [Objeto Icon] [Objeto]
```

### Ejemplo
```html
<img src="assets/actores/person.svg" width="20"> Empleado →
📝 Completa →
<img src="assets/objetos/form.svg" width="20"> Formulario
```

### Ejemplo Completo
```html
<img src="assets/actores/person.svg" width="20"> Empleado → 📝 Completa → <img src="assets/objetos/form.svg" width="20"> Formulario
<img src="assets/actores/person.svg" width="20"> Empleado → 📧 Envía → <img src="assets/objetos/document.svg" width="20"> Documento a supervisor
```

## Licencia

Estos iconos están basados en [Lucide Icons](https://lucide.dev/) y se pueden usar libremente para cualquier propósito.
