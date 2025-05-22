# DOCUMENTACIÓN TÉCNICA - HAIR CLUB APP

## 1. INFORMACIÓN GENERAL DEL PROYECTO

### Nombre del Proyecto
Hair Club - Sistema de Gestión para Peluquerías

### Descripción General
Hair Club es una aplicación web diseñada para gestionar 3 locales de peluquería, permitiendo a los clientes reservar citas online, comprar productos, acumular puntos de fidelización y gestionar su perfil. Los administradores podrán gestionar inventarios, empleados, horarios y generar reportes detallados.

### Objetivos Principales
- Centralizar la gestión de 3 locales de peluquería
- Facilitar la reserva de citas online
- Gestionar inventario y ventas por local
- Implementar sistema de fidelización
- Proporcionar herramientas de administración completas

---

## 2. ARQUITECTURA DEL SISTEMA

### Tecnologías Principales
- **Frontend**: React.js
- **Base de Datos**: MongoDB Atlas
- **Pagos**: Stripe
- **Notificaciones**: Email (futuro: SMS y WhatsApp)
- **Autenticación**: JWT

### Estructura de la Aplicación
```
Hair Club App
├── Panel de Usuario (Clientes)
├── Panel de Administración (Empleados)
└── Panel de Super Administración (Jefes/Propietarios)
```

---

## 3. GUÍA DE MARCA Y DISEÑO VISUAL

### Paleta de Colores Principal

#### Colores Corporativos
- **Blanco Premium**: #FFFFFF (Pure White)
- **Negro Elegante**: #000000 (Pure Black)
- **Dorado Brillante**: #FFD700 (Gold) / #F7D354 (Bright Gold)

#### Colores Complementarios
- **Gris Claro**: #F8F9FA (Backgrounds)
- **Gris Medio**: #6C757D (Text secundario)
- **Dorado Oscuro**: #B8860B (Hover states)

### Especificaciones de Diseño

#### Botones
- **Primarios**: Fondo dorado (#FFD700), texto negro, hover dorado oscuro (#B8860B)
- **Secundarios**: Borde dorado, fondo transparente, texto dorado
- **Terciarios**: Fondo negro, texto blanco, hover gris oscuro

#### Bordes y Radius
- **Border Radius**: 8px (estándar), 12px (tarjetas), 20px (botones redondeados)
- **Bordes**: 1px solid para elementos sutiles, 2px solid para elementos destacados

#### Tipografía
- **Principal**: Inter, Roboto, sans-serif
- **Tamaños**: 14px (texto), 16px (párrafos), 24px (subtítulos), 32px (títulos)

#### Espaciado
- **Padding**: 8px, 16px, 24px, 32px
- **Margin**: 8px, 16px, 24px, 32px, 48px

---

## 4. ESTRUCTURA DE USUARIOS

### Tipos de Usuario

#### 1. USERS (Clientes)
**Acceso**: Panel de Usuario
**Funcionalidades**:
- Registro y login
- Selección de local favorito/habitual
- Reserva de citas (1 mes de antelación)
- Compra de productos
- Acumulación y canje de puntos de fidelización
- Gestión de perfil personal

#### 2. ADMINS (Empleados)
**Acceso**: Panel de Administración
**Funcionalidades**:
- Dashboard con métricas del local asignado
- Gestión de calendario y citas
- Gestión de productos e inventario
- Gestión de servicios
- Visualización de usuarios del local
- Configuración básica del local

#### 3. SUPERADMINS (Jefes/Propietarios)
**Acceso**: Panel de Super Administración
**Funcionalidades**:
- Control total de los 3 locales
- Gestión de administradores y empleados
- Reportes consolidados y por local
- Configuración de puntos de fidelización
- Gestión de horarios especiales
- Facturación y métricas financieras
- Configuración global del sistema

---

## 5. FUNCIONALIDADES DETALLADAS

### 5.1 SISTEMA DE AUTENTICACIÓN
- **Registro**: Email, contraseña, datos personales
- **Login**: Email/contraseña con validación
- **Recuperación**: Envío de email para resetear contraseña
- **Selección de Local**: Al registrarse, elegir local favorito y habitual

### 5.2 SISTEMA DE CITAS

#### Reserva de Citas
- **Disponibilidad**: 1 mes de antelación máximo
- **Selección**: Local → Servicio → Empleado → Fecha/Hora
- **Información del Empleado**: Foto, presentación, horarios disponibles
- **Confirmación**: Email de confirmación automático

#### Gestión de Citas
- **Cancelación**: Mínimo 1 día de antelación
- **Penalización**: Reducción de puntos de fidelización por cancelaciones tardías
- **Recordatorios**: Email 24h antes de la cita
- **Estados**: Pendiente, Confirmada, Completada, Cancelada

### 5.3 SISTEMA DE PRODUCTOS

#### Catálogo de Productos
- **Filtros**: Por local, categoría, precio, disponibilidad
- **Información**: Imágenes, descripción, precio, stock
- **Puntos**: Puntos de fidelización que otorga cada producto

#### Carrito de Compras
- **Modalidades de Pago**:
  - Online con Stripe (tarjeta de crédito/débito)
  - Pago en local (efectivo/tarjeta)
- **Modalidades de Entrega**:
  - Recogida en local
  - Envío (futuro)

### 5.4 SISTEMA DE FIDELIZACIÓN

#### Acumulación de Puntos
- **Registro**: Puntos de bienvenida
- **Servicios**: Puntos por cada servicio completado
- **Productos**: Puntos por compras con dinero (no por canjes)

#### Canje de Puntos
- **Productos**: Intercambio de puntos por productos
- **Servicios**: Intercambio de puntos por servicios
- **Restricción**: No se otorgan puntos en compras con puntos

### 5.5 SISTEMA DE HORARIOS

#### Horarios por Local
- **Configuración Base**:
  - Horario de mañana (ej: 8:00-14:00)
  - Horario de tarde (ej: 15:00-20:00)
  - Horario continuo (ej: 8:00-20:00)

#### Horarios por Empleado
- **Asignación**: Cada empleado tiene horarios específicos
- **Personalización**: Modificación temporal de horarios
- **Disponibilidad**: Gestión de ausencias y disponibilidad

#### Horarios Especiales
- **Días Festivos**: Configuración de días cerrados/abiertos
- **Eventos Especiales**: Horarios específicos para fechas concretas
- **Modificaciones**: Cambios temporales en horarios establecidos

---

## 6. ESTRUCTURA DE NAVEGACIÓN

### 6.1 PANEL DE USUARIO (Clientes)

#### Página de Inicio (Home)
- Bienvenida personalizada
- Local seleccionado actual
- Próximas citas
- Ofertas y promociones
- Puntos de fidelización actuales

#### Productos
- Catálogo filtrado por local seleccionado
- Búsqueda y filtros avanzados
- Carrito de compras
- Historial de compras

#### Servicios
- Lista de servicios disponibles por local
- Precios y duración
- Puntos de fidelización por servicio
- Galería de trabajos realizados

#### Citas
- Reservar nueva cita
- Mis citas (próximas, historial)
- Cancelar/modificar citas
- Recordatorios

#### Perfil
- Datos personales
- Cambiar local favorito/habitual
- Historial de puntos
- Configuración de notificaciones
- Cerrar sesión

### 6.2 PANEL DE ADMINISTRACIÓN (Empleados)

#### Dashboard
- Métricas del día/semana/mes
- Citas pendientes
- Productos con stock bajo
- Actividad reciente

#### Calendario
- Vista mensual/semanal/diaria
- Gestión de citas
- Asignación de empleados
- Bloqueo de horarios

#### Productos
- Inventario del local
- Agregar/editar productos
- Control de stock
- Reportes de ventas

#### Servicios
- Gestión de servicios ofrecidos
- Precios por servicio
- Duración y empleados asignados
- Puntos de fidelización

#### Usuarios
- Lista de clientes del local
- Historial de servicios
- Puntos de fidelización
- Comunicación con clientes

#### Configuración
- Datos del local
- Horarios de atención
- Configuración de empleados
- Preferencias del sistema

### 6.3 PANEL DE SUPER ADMINISTRACIÓN (Jefes)

#### Dashboard Global
- Métricas consolidadas de los 3 locales
- Comparativas entre locales
- Tendencias y análisis
- KPIs principales

#### Gestión de Locales
- Configuración individual por local
- Asignación de administradores
- Horarios y configuraciones especiales
- Inventarios centralizados

#### Reportes Avanzados
- Reportes financieros consolidados
- Análisis de rendimiento por local
- Reportes de usuarios y fidelización
- Exportación de datos

#### Gestión de Personal
- Agregar/editar administradores
- Asignación de permisos
- Horarios de empleados
- Evaluación de rendimiento

#### Configuración Global
- Configuración del sistema
- Gestión de puntos de fidelización
- Políticas de cancelación
- Integraciones (Stripe, emails)

---

## 7. BASE DE DATOS - ESTRUCTURA

### Colecciones Principales

#### Users
```javascript
{
  _id: ObjectId,
  email: String,
  password: String (hashed),
  firstName: String,
  lastName: String,
  phone: String,
  dateOfBirth: Date,
  favoriteLocation: ObjectId,
  habitualLocation: ObjectId,
  loyaltyPoints: Number,
  role: String, // 'user', 'admin', 'superadmin'
  assignedLocation: ObjectId, // solo para admins
  createdAt: Date,
  updatedAt: Date,
  isActive: Boolean
}
```

#### Locations
```javascript
{
  _id: ObjectId,
  name: String,
  address: String,
  phone: String,
  email: String,
  schedule: {
    normal: {
      monday: { morning: {start: String, end: String}, afternoon: {start: String, end: String} },
      tuesday: { morning: {start: String, end: String}, afternoon: {start: String, end: String} },
      // ... resto de días
    },
    special: [{
      date: Date,
      isOpen: Boolean,
      schedule: { morning: {start: String, end: String}, afternoon: {start: String, end: String} }
    }]
  },
  employees: [ObjectId],
  isActive: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

#### Products
```javascript
{
  _id: ObjectId,
  name: String,
  description: String,
  price: Number,
  images: [String],
  stock: Number,
  category: String,
  loyaltyPoints: Number,
  location: ObjectId,
  isActive: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

#### Services
```javascript
{
  _id: ObjectId,
  name: String,
  description: String,
  price: Number,
  duration: Number, // en minutos
  loyaltyPoints: Number,
  location: ObjectId,
  availableEmployees: [ObjectId],
  images: [String],
  isActive: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

#### Appointments
```javascript
{
  _id: ObjectId,
  user: ObjectId,
  location: ObjectId,
  employee: ObjectId,
  service: ObjectId,
  date: Date,
  startTime: String,
  endTime: String,
  status: String, // 'pending', 'confirmed', 'completed', 'cancelled'
  notes: String,
  loyaltyPointsEarned: Number,
  createdAt: Date,
  updatedAt: Date
}
```

#### Orders
```javascript
{
  _id: ObjectId,
  user: ObjectId,
  location: ObjectId,
  products: [{
    product: ObjectId,
    quantity: Number,
    price: Number
  }],
  total: Number,
  paymentMethod: String, // 'stripe', 'cash', 'points'
  paymentStatus: String, // 'pending', 'paid', 'cancelled'
  deliveryMethod: String, // 'pickup', 'delivery'
  status: String, // 'pending', 'confirmed', 'ready', 'completed', 'cancelled'
  loyaltyPointsEarned: Number,
  loyaltyPointsUsed: Number,
  stripePaymentId: String,
  createdAt: Date,
  updatedAt: Date
}
```

#### Employees
```javascript
{
  _id: ObjectId,
  user: ObjectId,
  location: ObjectId,
  specialties: [String],
  schedule: {
    monday: { start: String, end: String, breaks: [{start: String, end: String}] },
    tuesday: { start: String, end: String, breaks: [{start: String, end: String}] },
    // ... resto de días
  },
  profileImage: String,
  bio: String,
  isActive: Boolean,
  createdAt: Date,
  updatedAt: Date
}
```

#### LoyaltyTransactions
```javascript
{
  _id: ObjectId,
  user: ObjectId,
  type: String, // 'earned', 'redeemed'
  points: Number,
  reason: String,
  relatedOrder: ObjectId,
  relatedAppointment: ObjectId,
  createdAt: Date
}
```

---

## 8. CASOS DE USO PRINCIPALES

### 8.1 Cliente Reserva una Cita
1. Cliente hace login
2. Selecciona su local favorito (o cambia de local)
3. Navega a "Citas" → "Reservar nueva cita"
4. Selecciona servicio deseado
5. Elige empleado (ve foto, bio, disponibilidad)
6. Selecciona fecha y hora disponible
7. Confirma la reserva
8. Recibe email de confirmación
9. 24h antes recibe recordatorio por email

### 8.2 Cliente Compra Productos
1. Cliente navega a "Productos"
2. Ve catálogo filtrado por su local seleccionado
3. Agrega productos al carrito
4. Procede al checkout
5. Elige método de pago (Stripe o pago en local)
6. Elige método de entrega (recogida en local)
7. Confirma la compra
8. Recibe confirmación y acumula puntos de fidelización

### 8.3 Administrador Gestiona Inventario
1. Admin hace login
2. Navega a "Productos"
3. Ve inventario de su local asignado
4. Agrega nuevo producto con imágenes y detalles
5. Establece stock y puntos de fidelización
6. Monitorea productos con stock bajo
7. Actualiza precios y disponibilidad

### 8.4 SuperAdmin Configura Horarios Especiales
1. SuperAdmin hace login
2. Navega a "Gestión de Locales"
3. Selecciona local específico
4. Va a "Horarios Especiales"
5. Agrega fecha especial (ej: día festivo)
6. Configura si está abierto/cerrado
7. Asigna empleados disponibles
8. Guarda configuración
9. Sistema actualiza disponibilidad automáticamente

---

## 9. SISTEMA DE NOTIFICACIONES

### Tipos de Notificaciones por Email

#### Para Clientes
- **Bienvenida**: Al registrarse
- **Confirmación de cita**: Al reservar
- **Recordatorio de cita**: 24h antes
- **Confirmación de compra**: Al comprar productos
- **Puntos ganados**: Al acumular puntos
- **Recuperación de contraseña**: Al solicitarla
- **Promociones**: Ofertas especiales (opcional)

#### Para Administradores
- **Nueva cita**: Cuando se reserva en su local
- **Cancelación**: Cuando se cancela una cita
- **Stock bajo**: Cuando productos tienen poco inventario
- **Nueva compra**: Cuando hay una venta online

#### Para SuperAdministradores
- **Reportes diarios**: Resumen de actividad
- **Nuevos usuarios**: Registro de nuevos clientes
- **Métricas semanales**: KPIs consolidados

### Plantillas de Email
- Diseño acorde a la marca (dorado, negro, blanco)
- Responsive para móvil y desktop
- Botones de acción claros
- Información de contacto de cada local

---

## 10. SISTEMA DE REPORTES

### 10.1 Reportes para Administradores

#### Métricas de Usuarios
- Total de usuarios registrados
- Usuarios nuevos por período
- Usuarios activos vs inactivos
- Distribución por local

#### Métricas de Citas
- Citas por día/semana/mes/año
- Citas completadas vs canceladas
- Citas por empleado
- Servicios más solicitados
- Horarios de mayor demanda

#### Métricas de Ventas
- Ventas totales por período
- Productos más vendidos
- Métodos de pago utilizados
- Ventas online vs presenciales

### 10.2 Reportes para SuperAdministradores

#### Reportes Consolidados
- Métricas comparativas entre locales
- Rendimiento por local
- Empleados más productivos
- Análisis de rentabilidad

#### Reportes Financieros
- Facturación por local y consolidada
- Análisis de costos y beneficios
- Proyecciones de ingresos
- ROI por local

#### Reportes de Fidelización
- Puntos otorgados vs canjeados
- Usuarios más fieles
- Efectividad del programa de puntos
- Análisis de retención

---

## 11. INTEGRACIÓN DE PAGOS (STRIPE)

### Configuración de Stripe
- Cuenta Stripe Connect para manejar múltiples locales
- Webhooks para confirmación de pagos
- Manejo de reembolsos automáticos
- Seguridad PCI compliant

### Flujo de Pago
1. Cliente selecciona productos/servicios
2. Procede al checkout
3. Ingresa datos de tarjeta (formulario seguro de Stripe)
4. Stripe procesa el pago
5. Webhook confirma el pago exitoso
6. Sistema actualiza el pedido/cita
7. Se envía confirmación al cliente
8. Se acumulan puntos de fidelización

### Métodos de Pago Soportados
- Tarjetas de crédito/débito
- Pago en local (efectivo/tarjeta)
- Canje por puntos de fidelización

---

## 12. SEGURIDAD Y PRIVACIDAD

### Medidas de Seguridad
- **Autenticación**: JWT con expiración
- **Encriptación**: Contraseñas hasheadas con bcrypt
- **HTTPS**: Comunicación segura obligatoria
- **Validación**: Input validation en frontend y backend
- **Rate Limiting**: Prevención de ataques de fuerza bruta

### Protección de Datos
- **GDPR Compliance**: Manejo según regulaciones
- **Consentimientos**: Políticas de privacidad claras
- **Backups**: Copias de seguridad automáticas
- **Logs**: Registro de actividades críticas

---

## 13. PLAN DE DESARROLLO POR FASES

### FASE 1: MVP (Minimum Viable Product) - 8-10 semanas
#### Funcionalidades Core
- Sistema de autenticación básico
- Panel de usuario con funciones esenciales
- Sistema de citas básico
- Panel de administración básico
- Integración con MongoDB Atlas
- Diseño responsive básico

#### Entregables
- Registro y login de usuarios
- Reserva de citas simple
- Gestión básica de productos
- Panel administrativo básico

### FASE 2: Funcionalidades Avanzadas - 6-8 semanas
#### Características Adicionales
- Sistema de fidelización completo
- Integración de pagos con Stripe
- Sistema de notificaciones por email
- Reportes básicos
- Gestión avanzada de horarios

#### Entregables
- Carrito de compras funcional
- Sistema de puntos operativo
- Emails automáticos
- Reportes para administradores

### FASE 3: Optimización y Expansión - 4-6 semanas
#### Mejoras y Refinamientos
- Panel de SuperAdmin completo
- Reportes avanzados
- Optimización de rendimiento
- Sistema de horarios complejos
- Funcionalidades adicionales

#### Entregables
- Sistema completamente funcional
- Todas las funcionalidades implementadas
- Testing completo
- Documentación de usuario

### FASE 4: Lanzamiento y Mantenimiento - Continuo
#### Actividades Post-Lanzamiento
- Monitoreo del sistema
- Corrección de bugs
- Mejoras basadas en feedback
- Nuevas funcionalidades
- Soporte técnico

---

## 14. REQUERIMIENTOS TÉCNICOS

### Tecnologías del Frontend
- **React.js** (versión 18+)
- **React Router** para navegación
- **Context API** o **Redux** para estado global
- **Axios** para peticiones HTTP
- **Material-UI** o **Tailwind CSS** para componentes
- **React Hook Form** para formularios
- **Date-fns** para manejo de fechas

### Tecnologías del Backend
- **Node.js** con **Express.js**
- **MongoDB** con **Mongoose ODM**
- **JWT** para autenticación
- **Bcrypt** para encriptación de contraseñas
- **Stripe SDK** para pagos
- **Nodemailer** para emails
- **Multer** para subida de archivos
- **Cors** para políticas de origen cruzado

### Infraestructura
- **MongoDB Atlas** (base de datos cloud)
- **Cloudinary** o **AWS S3** (almacenamiento de imágenes)
- **Heroku/Vercel/Netlify** (hosting)
- **SendGrid/Mailgun** (servicio de emails)

### Herramientas de Desarrollo
- **Git** y **GitHub** para control de versiones
- **ESLint** y **Prettier** para código limpio
- **Jest** para testing
- **Postman** para testing de APIs

---

## 15. ESTRUCTURA DE ARCHIVOS SUGERIDA

```
hair-club-app/
├── client/                          # Frontend React
│   ├── public/
│   ├── src/
│   │   ├── components/              # Componentes reutilizables
│   │   │   ├── common/              # Componentes generales
│   │   │   ├── user/                # Componentes del panel usuario
│   │   │   ├── admin/               # Componentes del panel admin
│   │   │   └── superadmin/          # Componentes del panel superadmin
│   │   ├── pages/                   # Páginas principales
│   │   │   ├── auth/                # Login, registro
│   │   │   ├── user/                # Páginas del usuario
│   │   │   ├── admin/               # Páginas del admin
│   │   │   └── superadmin/          # Páginas del superadmin
│   │   ├── hooks/                   # Custom hooks
│   │   ├── context/                 # Context API
│   │   ├── services/                # Servicios API
│   │   ├── utils/                   # Utilidades
│   │   ├── styles/                  # Estilos globales
│   │   └── assets/                  # Imágenes, iconos
│   ├── package.json
│   └── ...
│
├── server/                          # Backend Node.js
│   ├── controllers/                 # Controladores
│   ├── models/                      # Modelos de MongoDB
│   ├── routes/                      # Rutas de la API
│   ├── middleware/                  # Middlewares
│   ├── utils/                       # Utilidades del servidor
│   ├── config/                      # Configuraciones
│   ├── uploads/                     # Archivos subidos
│   ├── package.json
│   └── server.js
│
├── docs/                            # Documentación
├── README.md
└── .gitignore
```

---

## 16. CONSIDERACIONES FUTURAS

### Expansiones Planificadas
- **Aplicación móvil**: iOS y Android nativas
- **Más idiomas**: Inglés, francés, etc.
- **Integración SMS**: Notificaciones por mensaje
- **WhatsApp Business**: Comunicación directa
- **Delivery**: Entrega a domicilio de productos
- **Video consultas**: Asesoramiento online
- **IA/Chatbot**: Asistente virtual para clientes

### Optimizaciones Técnicas
- **CDN**: Para carga rápida de imágenes
- **Caché**: Redis para mejorar rendimiento
- **Microservicios**: Escalabilidad de la arquitectura
- **Analytics**: Google Analytics, Mixpanel
- **Monitoring**: Sentry para errores en producción

### Funcionalidades Adicionales
- **Reviews**: Sistema de reseñas y calificaciones
- **Galería**: Portfolio de trabajos realizados
- **Blog**: Consejos de belleza y cuidado capilar
- **Membresías**: Planes premium para clientes VIP
- **Referidos**: Sistema de referidos con recompensas

---

## 17. MÉTRICAS DE ÉXITO

### KPIs Principales
- **Usuarios registrados**: Meta mensual de nuevos usuarios
- **Tasa de retención**: % de usuarios que regresan
- **Citas completadas**: % de citas que se completan vs canceladas
- **Revenue por usuario**: Gasto promedio por cliente
- **Net Promoter Score**: Satisfacción del cliente

### Métricas Operacionales
- **Tiempo de carga**: < 3 segundos
- **Uptime**: 99.9% disponibilidad
- **Conversion rate**: % de visitantes que reservan cita
- **Abandono de carrito**: % de carritos no completados

---

## 18. CONTACTO Y SOPORTE

### Información de Desarrollo
- **Desarrollador Principal**: [Tu nombre]
- **Email de contacto**: [Tu email]
- **Repositorio**: [Link a GitHub]
- **Documentación técnica**: [Link a documentación]

### Soporte Post-Lanzamiento
- **Canal de soporte**: Email, telefónico
- **Horarios de soporte**: Lunes a viernes 9:00-18:00
- **Tiempo de respuesta**: 24-48 horas
- **Actualizaciones**: Mensuales con mejoras y correcciones

---

## 19. CONCLUSIÓN

La aplicación Hair Club representa una solución integral para la gestión moderna de peluquerías múltiples. Con un enfoque en la experiencia del usuario, eficiencia operacional y escalabilidad técnica, esta plataforma permitirá a Hair Club competir efectivamente en el mercado digital mientras mantiene la calidad del servicio personalizado.

El desarrollo por fases asegura un lanzamiento controlado y permite iteraciones basadas en feedback real de usuarios. La arquitectura técnica propuesta garantiza escalabilidad y mantenibilidad a largo plazo.

La implementación exitosa de este sistema resultará en:
- Mayor satisfacción del cliente
- Optimización de operaciones
- Aumento en ventas y fidelización
- Ventaja competitiva en el mercado
- Base sólida para futuras expansiones

---

**Documento versión 1.0**
**Fecha de creación**: Mayo 2025
**Última actualización**: Mayo 2025

---

*Este documento es un trabajo en progreso y será actualizado según evolucionen los requerimientos del proyecto.*