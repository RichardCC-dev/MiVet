# 🐾 MiVet - Sistema de Gestión Veterinaria con IA

<div align="center">

![Node.js](https://img.shields.io/badge/Node.js-18+-339933?style=for-the-badge&logo=node.js&logoColor=white)
![React](https://img.shields.io/badge/React-18-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![MySQL](https://img.shields.io/badge/MySQL-8+-4479A1?style=for-the-badge&logo=mysql&logoColor=white)


**Sistema web completo de gestión veterinaria integrado con IA para chatbot inteligente**

[Demo](#) · [Documentación](docs/) · [Reportar Bug](../../issues) · [Solicitar Feature](../../issues)

</div>

---

## 📋 Descripción

MiVet es una plataforma web full-stack que permite gestionar todos los aspectos de una clínica veterinaria:

- 👥 Gestión de usuarios con roles (Admin, Veterinario, Recepcionista, Groomer, Cliente)
- 🐕 Registro y seguimiento de mascotas
- 📅 Sistema de citas con calendario interactivo
- 🏥 Historial médico completo
- 💊 Gestión de inventario de productos
- 💰 Módulo de ventas y pagos (integración con Stripe)
- 🤖 Chatbot inteligente con IA (Gemini)
- 📊 Dashboard y reportes personalizados
- 📧 Notificaciones por email

## 🛠️ Tecnologías

<div align="center">

### Backend
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Express.js](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Sequelize](https://img.shields.io/badge/Sequelize-52B0E7?style=for-the-badge&logo=sequelize&logoColor=white)
![JWT](https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-008CDD?style=for-the-badge&logo=stripe&logoColor=white)

### Frontend
![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![Vite](https://img.shields.io/badge/Vite-646CFF?style=for-the-badge&logo=vite&logoColor=white)
![Material-UI](https://img.shields.io/badge/Material--UI-007FFF?style=for-the-badge&logo=mui&logoColor=white)
![React Router](https://img.shields.io/badge/React_Router-CA4245?style=for-the-badge&logo=react-router&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white)

</div>

---

## ✨ Características Principales

✅ **Autenticación Segura** - Sistema de roles y permisos con JWT  
✅ **Gestión Integral** - Mascotas, citas, inventario y ventas  
✅ **Calendario Interactivo** - Visualización y gestión de citas en tiempo real  
✅ **Historial Médico** - Registro completo de consultas y tratamientos  
✅ **Chatbot IA** - Asistente inteligente para consultas veterinarias  
✅ **Pagos Online** - Integración con Stripe para pagos seguros  
✅ **Reportes y Análisis** - Dashboard con métricas y estadísticas  
✅ **Notificaciones** - Sistema automatizado de recordatorios por email  

## 📁 Estructura del Proyecto

```
MiVet/
├── backend/          # API REST en Node.js
│   ├── src/
│   │   ├── api/
│   │   │   ├── controllers/
│   │   │   ├── models/
│   │   │   └── routes/
│   │   ├── config/
│   │   ├── middlewares/
│   │   └── utils/
│   └── package.json
│
├── frontend/         # Aplicación React
│   ├── src/
│   │   ├── components/
│   │   ├── features/
│   │   ├── pages/
│   │   └── routes/
│   └── package.json
│
└── docs/            # Documentación del proyecto
```

## 🚀 Instalación y Configuración

### Prerrequisitos

- Node.js (v18 o superior)
- MySQL (v8 o superior)
- Git

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu-usuario/MiVet.git
cd MiVet
```

### 2. Configurar el Backend

```bash
cd backend
npm install
```

Crear archivo `.env` en la carpeta `backend` (usar `.env.example` como plantilla):

```env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=tu_password
DB_NAME=mivet_db
DB_PORT=3306
JWT_SECRET=tu_secreto_jwt
STRIPE_SECRET_KEY=tu_clave_stripe
GEMINI_API_KEY=tu_api_key_gemini
# ... ver .env.example para más variables
```

### 3. Configurar la Base de Datos

```bash
# Crear la base de datos en MySQL
mysql -u root -p
CREATE DATABASE mivet_db;
exit
```

### 4. Configurar el Frontend

```bash
cd ../frontend
npm install
```

Crear archivo `.env` en la carpeta `frontend`:

```env
VITE_API_URL=http://localhost:3000/api
VITE_STRIPE_PUBLISHABLE_KEY=tu_clave_publica_stripe
```

### 5. Iniciar el Proyecto

En dos terminales diferentes:

**Terminal 1 - Backend:**
```bash
cd backend
npm run dev
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm run dev
```

La aplicación estará disponible en:
- Frontend: http://localhost:5173
- Backend API: http://localhost:3000

## 👥 Roles del Sistema

| Rol | Descripción |
|-----|-------------|
| **Admin** | Acceso total al sistema, gestión de usuarios y configuración |
| **Veterinario** | Gestión de citas, historial médico y recetas |
| **Recepcionista** | Gestión de citas, clientes y pagos |
| **Groomer** | Gestión de servicios de estética |
| **Cliente** | Gestión de sus mascotas y citas |

## 📚 Documentación Adicional

- 📋 [Requisitos del Sistema](docs/requisitos.md)
- 🎯 [Product Backlog](docs/product_backlog.md)
- 🎨 [Diseño UI/UX](docs/diseño_ui_ux.md)
- ⚡ [Guía de Instalación Rápida](QUICK_START.md)
- 🚀 [Guía de Despliegue](DEPLOYMENT.md)

## 🎓 Sobre el Proyecto

Este proyecto fue desarrollado como parte de un trabajo académico del curso de **Taller de Construcción Web (TCW)**, demostrando habilidades en:

- 🏗️ **Arquitectura Full-Stack** - Diseño e implementación de API REST y SPA
- 🔐 **Seguridad** - Autenticación JWT, encriptación, validación de datos
- 🗄️ **Bases de Datos** - Modelado, relaciones y optimización de consultas
- 🤖 **Integración de IA** - Implementación de chatbot con Gemini
- 💳 **APIs de Terceros** - Integración de pagos con Stripe
- 📱 **Responsive Design** - Interfaz adaptable con Material-UI
- 🧪 **Buenas Prácticas** - Clean Code, estructura modular, documentación

### 🎯 Objetivos de aprendizaje alcanzados

- Desarrollo de aplicaciones web escalables y mantenibles
- Implementación de sistemas de autenticación y autorización
- Integración de servicios externos y APIs
- Gestión de estado y routing en aplicaciones React
- Diseño de bases de datos relacionales
- Metodologías ágiles y gestión de proyectos


## 👨‍💻 Autor

**Estudiante de Ingeniería de Software**  
Proyecto académico - Taller de Construcción Web (TCW)  
Universidad: Universidad Nacional Mayor de San Marcos (UNMSM)  
Año: 2025-II

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/tu-perfil)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/tu-usuario)
[![Portfolio](https://img.shields.io/badge/Portfolio-255E63?style=for-the-badge&logo=About.me&logoColor=white)](https://tu-portfolio.com)

## 📧 Contacto

Para oportunidades de prácticas profesionales, colaboraciones o consultas sobre el proyecto:

- 📧 Email: jricastica90@gmail.com
- 💼 LinkedIn: [Jose Richard Castillo Carranza](https://www.linkedin.com/in/jose-richard-castillo-carranza-403169282/)
- 🌐 Portfolio: 

---

<div align="center">

**⭐ Si este proyecto te pareció interesante, considera darle una estrella en GitHub ⭐**

Made with ❤️ by Jose Richard Castillo Carranza

</div>
