# Hair Club - Aplicación Web para Peluquería

## 📋 Descripción del Proyecto

Hair Club es una aplicación web moderna desarrollada específicamente para la peluquería Hair Club y sus tres locales. La plataforma permite a los clientes de Hair Club reservar citas online para cualquier servicio, comprar productos de la peluquería, acumular puntos de fidelización y gestionar su perfil personal, mientras que los administradores pueden gestionar inventarios, empleados, horarios y generar reportes detallados de cada local.

## ✨ Características Principales

### Para Clientes
- 🔐 **Sistema de autenticación** - Registro y login seguro
- ✂️ **Servicios de peluquería** - Reserva citas para cortes, peinados, tratamientos, coloración, mechas, alisados, permanentes y más
- 📅 **Reserva de citas online** - Reserva cualquier servicio hasta 1 mes de antelación
- 🛍️ **Catálogo de productos Hair Club** - Productos exclusivos de la peluquería disponibles para compra
- 🛒 **Carrito de compras inteligente** - Agrega productos y procede al pago de forma sencilla
- 💳 **Múltiples formas de pago** - Pago online con tarjeta o pago directo en el local (efectivo/tarjeta)
- ⭐ **Sistema de fidelización** - Acumula y canje puntos por servicios y productos
- 👤 **Gestión de perfil** - Administra tus datos y preferencias
- 📍 **Selección de peluquería favorita** - Elige entre los 3 locales de Hair Club tu favorito

### Para Administradores
- 📊 **Dashboard completo** - Métricas y KPIs de su local asignado
- 🗓️ **Gestión de calendario** - Control total de citas y horarios del local
- 📦 **Inventario inteligente** - Gestión de productos Hair Club y stock del local
- 👥 **Gestión de usuarios** - Administración de clientes del local Hair Club
- ⚙️ **Configuración flexible** - Horarios, servicios y empleados del local

### Para Super Administradores
- 🏢 **Control de los 3 locales Hair Club** - Gestión centralizada de todos los locales
- 📈 **Reportes avanzados** - Análisis consolidado y comparativo entre locales
- 👨‍💼 **Gestión de personal** - Administración de empleados y permisos de Hair Club
- 💰 **Métricas financieras** - Facturación y análisis de rentabilidad de los locales

## 🎨 Diseño y Marca

### Paleta de Colores
- **Blanco Premium:** #FFFFFF
- **Negro Elegante:** #000000  
- **Dorado Brillante:** #FFD700
- **Gris Claro:** #F8F9FA
- **Gris Medio:** #6C757D

### Principios de Diseño
- Interfaz moderna y elegante
- Diseño responsive para todos los dispositivos
- Experiencia de usuario intuitiva
- Branding consistente en toda la aplicación

## 🛠️ Stack Tecnológico

### Frontend
- **React.js** - Biblioteca para interfaces de usuario
- **React Router** - Navegación entre páginas
- **Axios** - Cliente HTTP para APIs
- **Material-UI / Tailwind CSS** - Componentes y estilos

### Backend
- **Node.js** - Entorno de ejecución JavaScript
- **Express.js** - Framework web para Node.js
- **MongoDB** - Base de datos NoSQL
- **Mongoose** - ODM para MongoDB

### Servicios Externos
- **MongoDB Atlas** - Base de datos en la nube
- **Stripe** - Procesamiento de pagos
- **Cloudinary** - Gestión de imágenes
- **SendGrid** - Servicio de emails

### Herramientas de Desarrollo
- **JWT** - Autenticación segura
- **Bcrypt** - Encriptación de contraseñas
- **ESLint & Prettier** - Calidad de código
- **Jest** - Testing

## 🏗️ Arquitectura del Sistema

```
Hair Club App
├── Panel de Cliente
│   ├── Gestión de perfil
│   ├── Reserva de citas (todos los servicios)
│   ├── Catálogo de productos Hair Club
│   ├── Sistema de fidelización
│   └── Selección de local favorito
├── Panel de Administración (Empleados)
│   ├── Dashboard del local asignado
│   ├── Gestión de citas del local
│   ├── Inventario de productos Hair Club
│   └── Configuración del local
└── Panel de Super Administración (Propietarios)
    ├── Control de los 3 locales Hair Club
    ├── Reportes consolidados
    ├── Gestión de personal
    └── Configuración global
```

## 📁 Estructura del Proyecto

```
hair-club-app/
├── client/                 # Frontend React
│   ├── src/
│   │   ├── components/     # Componentes reutilizables
│   │   ├── pages/         # Páginas principales
│   │   ├── hooks/         # Custom hooks
│   │   ├── services/      # Servicios API
│   │   └── utils/         # Utilidades
│   └── package.json
├── server/                # Backend Node.js
│   ├── controllers/       # Controladores
│   ├── models/           # Modelos de MongoDB
│   ├── routes/           # Rutas de la API
│   ├── middleware/       # Middlewares
│   └── config/           # Configuraciones
└── docs/                 # Documentación
```

## 🚀 Instalación y Configuración

### Prerrequisitos
- Node.js (versión 14 o superior)
- MongoDB (local o Atlas)
- Cuenta de Stripe para pagos
- Cuenta de SendGrid para emails

### Instalación

1. **Clonar el repositorio**
```bash
git clone https://github.com/karimkron/HairClub
cd HairClub
```

2. **Instalar dependencias del servidor**
```bash
cd .\peluqueria_backend\
npm install
```

3. **Instalar dependencias del cliente**
```bash
cd .\peluqueria_dashboard\
npm install
```
4. **Instalar dependencias del Admin panel**
```bash
cd .\peluqueria_admin\
npm install
```

5. **Configurar variables de entorno**
```bash
# En la carpeta server, crear archivo .env
cp .env.example .env
# Editar .env con tus configuraciones
```

6. **Iniciar el servidor de desarrollo**
```bash
# Terminal 1 - Backend
npm run dev

# Terminal 2 - Frontend
npm run dev
```
# Terminal 3 - Admin panel
npm run dev
```

## 📱 Funcionalidades Detalladas

### Sistema de Citas
- Selección de local Hair Club, servicio y empleado
- **Servicios disponibles:** Cortes de cabello, peinados, tratamientos capilares, coloración, mechas, alisados, permanentes, lavado y secado
- Calendario interactivo con disponibilidad en tiempo real
- **Reserva hasta 1 mes de antelación** para cualquier servicio
- Confirmaciones automáticas por email
- Recordatorios 24h antes de la cita
- Gestión de cancelaciones con políticas flexibles

### Sistema de Productos
- **Catálogo exclusivo de productos Hair Club** - Productos de la peluquería
- Catálogo filtrable por categorías y local
- **Carrito de compras inteligente** - Agrega múltiples productos
- **Múltiples métodos de pago:**
  - 💳 **Pago online** - Tarjeta de crédito/débito a través de Stripe
  - 🏪 **Pago en local** - Efectivo o tarjeta directamente en la peluquería
  - ⭐ **Pago con puntos** - Canje de puntos de fidelización
- Gestión de inventario en tiempo real por local
- Sistema de puntos por compras

### Sistema de Fidelización
- Puntos por servicios completados
- Puntos por compras de productos
- Canje por servicios y productos
- Historial completo de transacciones
- Niveles de fidelización

## 🔒 Seguridad

- Autenticación JWT con tokens seguros
- Encriptación de contraseñas con bcrypt
- Validación de datos en frontend y backend
- Comunicación HTTPS obligatoria
- Cumplimiento con estándares de privacidad

## 📊 Plan de Desarrollo

### Fase 1: MVP (8-10 semanas)
- ✅ Sistema de autenticación
- ✅ Reserva de citas básica
- ✅ Gestión de productos
- ✅ Panel administrativo

### Fase 2: Funcionalidades Avanzadas (6-8 semanas)
- 🔄 Sistema de fidelización
- 🔄 Integración de pagos
- 🔄 Notificaciones por email
- 🔄 Reportes básicos

### Fase 3: Optimización (4-6 semanas)
- ⏳ Panel de SuperAdmin
- ⏳ Reportes avanzados
- ⏳ Optimización de rendimiento
- ⏳ Testing completo

## 🤝 Contribución

Las contribuciones son bienvenidas. Por favor, sigue estos pasos:

1. Fork el proyecto
2. Crea una rama para tu característica (`git checkout -b feature/nueva-caracteristica`)
3. Commit tus cambios (`git commit -m 'Agregar nueva característica'`)
4. Push a la rama (`git push origin feature/nueva-caracteristica`)
5. Abre un Pull Request

## 📋 Requisitos del Sistema

### Mínimos
- Node.js 14+
- MongoDB 4.4+
- 2GB RAM
- 10GB espacio en disco

### Recomendados
- Node.js 18+
- MongoDB 5.0+
- 4GB RAM
- 20GB espacio en disco

## 📞 Soporte

Para soporte técnico o consultas sobre el proyecto:

- 📧 Email: berbkarim@gmail.com    
- 📚 Documentación: Actualizado

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Ver el archivo `LICENSE` para más detalles.

## 🙏 Agradecimientos

- Equipo de Hair Club por la confianza en el proyecto
- Comunidad de React.js por las herramientas increíbles
- Contribuidores y testers del proyecto

---

**Hair Club** - Transformando la gestión de peluquerías con tecnología moderna ✨

*Última actualización: Mayo 2025*
