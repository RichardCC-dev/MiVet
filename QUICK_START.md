# 🚀 Instalación Rápida - MiVet

Guía rápida para poner el proyecto en funcionamiento en minutos.

## Prerrequisitos

- [Node.js](https://nodejs.org/) v18 o superior
- [MySQL](https://www.mysql.com/) v8 o superior  
- [Git](https://git-scm.com/)

## Instalación en 5 Pasos

### 1️⃣ Clonar el Repositorio

```bash
git clone https://github.com/RichardCC-dev/MiVet.git
cd MiVet
```

### 2️⃣ Configurar Backend

```bash
cd backend
npm install
cp .env.example .env
```

Edita el archivo `backend/.env` con tus credenciales:
```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=tu_password
DB_NAME=mivet_db
JWT_SECRET=genera_un_secreto_aleatorio
```

### 3️⃣ Crear Base de Datos

```bash
mysql -u root -p
```

```sql
CREATE DATABASE mivet_db;
EXIT;
```

### 4️⃣ Configurar Frontend

```bash
cd ../frontend
npm install
cp .env.example .env
```

El archivo `frontend/.env` debería tener:
```env
VITE_API_URL=http://localhost:3000/api
```

### 5️⃣ Iniciar el Proyecto

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

## 🎉 ¡Listo!

Abre tu navegador en:
- **Frontend:** http://localhost:5173
- **Backend API:** http://localhost:3000

## 📝 Usuarios de Prueba

El sistema creará un usuario administrador por defecto:
- **Email:** admin@mivet.com
- **Password:** admin123

## ⚙️ Configuraciones Opcionales

### Stripe (Pagos)
Para habilitar pagos, obtén tus claves en [Stripe Dashboard](https://dashboard.stripe.com/):
```env
STRIPE_SECRET_KEY=sk_test_...
STRIPE_PUBLISHABLE_KEY=pk_test_...
```

### Gemini (Chatbot IA)
Para el chatbot, obtén un token en [Gemini](https://aistudio.google.com/api-keys):
```env
GEMINI_API_KEY=...
```

### Email (Notificaciones)
Para notificaciones por email:
```env
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=tu_email@gmail.com
EMAIL_PASS=tu_app_password
```

## 🐛 Problemas Comunes

### Error de conexión a MySQL
- Verifica que MySQL esté corriendo: `mysql -u root -p`
- Confirma las credenciales en `.env`

### Puerto 3000 o 5173 en uso
Cambia el puerto en:
- Backend: `backend/.env` → `PORT=3001`
- Frontend: `frontend/vite.config.js`

### Error de módulos
```bash
rm -rf node_modules package-lock.json
npm install
```

## 📚 Más Información

- [README completo](README.md)
- [Documentación](docs/)
- [Contribuir](CONTRIBUTING.md)

