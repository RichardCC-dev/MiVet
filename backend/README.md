# Backend MiVet

API REST para el sistema de gestión veterinaria MiVet.

## 🛠️ Tecnologías

- Node.js + Express.js
- MySQL + Sequelize ORM
- JWT para autenticación
- Stripe para pagos
- Gemini API para IA
- Nodemailer para emails

## 📦 Instalación

```bash
npm install
```

## ⚙️ Configuración

1. Copia el archivo `.env.example` a `.env`
2. Configura las variables de entorno según tu entorno

```bash
cp .env.example .env
```

Variables requeridas:
- `DB_*`: Credenciales de MySQL
- `JWT_SECRET`: Clave secreta para tokens
- `STRIPE_SECRET_KEY`: Clave de Stripe
- `Gemini_API_KEY`: Token de Gemini

## 🗄️ Base de Datos

Crear la base de datos en MySQL:

```sql
CREATE DATABASE mivet_db;
```

Las tablas se crearán automáticamente al iniciar el servidor.

## 🚀 Uso

### Modo desarrollo
```bash
npm run dev
```

### Modo producción
```bash
npm start
```

El servidor se iniciará en `http://localhost:3000`

## 📁 Estructura

```
src/
├── api/
│   ├── controllers/    # Lógica de negocio
│   ├── models/        # Modelos de Sequelize
│   └── routes/        # Rutas de la API
├── config/            # Configuración
├── middlewares/       # Middlewares personalizados
├── services/          # Servicios (cron, etc.)
└── utils/             # Utilidades
```

## 🔐 Autenticación

La API usa JWT para autenticación. Include el token en el header:

```
Authorization: Bearer <token>
```

## 📝 Endpoints Principales

### Autenticación
- `POST /api/auth/register` - Registro
- `POST /api/auth/login` - Login
- `POST /api/auth/logout` - Logout

### Usuarios
- `GET /api/users` - Listar usuarios
- `PUT /api/users/:id` - Actualizar usuario

### Mascotas
- `GET /api/pets` - Listar mascotas
- `POST /api/pets` - Crear mascota
- `PUT /api/pets/:id` - Actualizar mascota
- `DELETE /api/pets/:id` - Eliminar mascota

### Citas
- `GET /api/appointments` - Listar citas
- `POST /api/appointments` - Crear cita
- `PUT /api/appointments/:id` - Actualizar cita
- `DELETE /api/appointments/:id` - Cancelar cita

Ver documentación completa de endpoints en `/docs`
