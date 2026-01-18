# 🚀 Guía de Despliegue - MiVet

Esta guía detalla cómo desplegar MiVet en diferentes plataformas para producción.

## 📋 Tabla de Contenidos

- [Preparación](#preparación)
- [Despliegue Backend](#despliegue-backend)
- [Despliegue Frontend](#despliegue-frontend)
- [Configuración de Base de Datos](#configuración-de-base-de-datos)
- [Variables de Entorno](#variables-de-entorno)

## 🔧 Preparación

### Requisitos Previos

- Node.js 18+ instalado
- Cuenta en servicios de hosting (sugerencias abajo)
- Base de datos MySQL en producción
- Claves de API (Stripe, Gemini) configuradas

## 🖥️ Despliegue Backend

### Opción 1: Railway

1. Instalar Railway CLI:
```bash
npm install -g @railway/cli
```

2. Iniciar sesión y desplegar:
```bash
cd backend
railway login
railway init
railway up
```

3. Configurar variables de entorno en Railway dashboard

### Opción 2: Render

1. Conectar repositorio en [Render.com](https://render.com)
2. Seleccionar "New Web Service"
3. Configurar:
   - **Build Command:** `npm install`
   - **Start Command:** `npm start`
   - **Environment:** Node
4. Agregar variables de entorno

### Opción 3: Heroku

```bash
cd backend
heroku login
heroku create mivet-api
git push heroku main
heroku config:set DB_HOST=your_host
# ... configurar otras variables
```

## 🌐 Despliegue Frontend

### Opción 1: Vercel (Recomendado)

1. Instalar Vercel CLI:
```bash
npm install -g vercel
```

2. Desplegar:
```bash
cd frontend
vercel
```

3. Configurar variables de entorno:
```bash
vercel env add VITE_API_URL
```

### Opción 2: Netlify

1. Build del proyecto:
```bash
cd frontend
npm run build
```

2. Desplegar con Netlify CLI:
```bash
npm install -g netlify-cli
netlify deploy --prod --dir=dist
```

3. Configurar variables en Netlify dashboard

## 🗄️ Configuración de Base de Datos

### Opciones de Hosting MySQL

1. **PlanetScale** (Recomendado - Free tier)
   - Crea cuenta en [planetscale.com](https://planetscale.com)
   - Crea nueva base de datos
   - Obtén connection string
   - Configura en variables de entorno

2. **Railway MySQL**
   ```bash
   railway add mysql
   ```

3. **AWS RDS**
   - Crea instancia MySQL en RDS
   - Configura Security Groups
   - Conecta con variables de entorno

## ⚙️ Variables de Entorno

### Backend (Producción)

```env
NODE_ENV=production
PORT=3000
DB_HOST=tu-host-produccion.com
DB_USER=usuario_produccion
DB_PASSWORD=contraseña_segura
DB_NAME=mivet_production
DB_PORT=3306
JWT_SECRET=secreto_muy_seguro_diferente_a_dev
STRIPE_SECRET_KEY=sk_live_...
STRIPE_WEBHOOK_SECRET=whsec_...
GEMINI_API_KEY=...
FRONTEND_URL=https://mivet.vercel.app
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=587
EMAIL_USER=noreply@tudominio.com
EMAIL_PASS=contraseña_app
```

### Frontend (Producción)

```env
VITE_API_URL=https://mivet-api.railway.app/api
VITE_STRIPE_PUBLISHABLE_KEY=pk_live_...
VITE_NODE_ENV=production
```

## 🔐 Checklist de Seguridad

Antes de desplegar:

- [ ] Cambiar todos los secretos de desarrollo
- [ ] Activar HTTPS en producción
- [ ] Configurar CORS correctamente
- [ ] Habilitar rate limiting
- [ ] Revisar logs de errores
- [ ] Configurar backups de base de datos
- [ ] Actualizar dependencias vulnerables
- [ ] Eliminar logs de desarrollo/debug

## 📊 Monitoreo

### Herramientas Recomendadas

- **Logs:** Railway/Render logs, LogRocket
- **Errores:** Sentry
- **Performance:** New Relic, DataDog
- **Uptime:** UptimeRobot, Pingdom

## 🔄 CI/CD con GitHub Actions

Ya incluido en `.github/workflows/ci.yml`. Se ejecuta automáticamente en cada push.

Para despliegue automático, agrega secrets en GitHub:
- `VERCEL_TOKEN`
- `RAILWAY_TOKEN`
- `RENDER_API_KEY`

## 📝 Post-Despliegue

1. **Verificar endpoints:**
   ```bash
   curl https://tu-api.com/api/health
   ```

2. **Probar autenticación:**
   - Registro de usuario
   - Login
   - Acceso a rutas protegidas

3. **Verificar integraciones:**
   - Pagos con Stripe
   - Chatbot con Gemini
   - Envío de emails

4. **Monitorear métricas:**
   - Tiempo de respuesta
   - Tasa de errores
   - Uso de recursos

## 🆘 Solución de Problemas

### Error de CORS
```javascript
// backend/src/app.js
app.use(cors({
  origin: process.env.FRONTEND_URL,
  credentials: true
}));
```

### Error de Base de Datos
- Verificar connection string
- Comprobar whitelisting de IP
- Revisar credenciales

### Build Frontend Falla
```bash
# Limpiar y reinstalar
rm -rf node_modules package-lock.json
npm install
npm run build
```

## 🎯 Arquitectura en Producción

```
[Cliente]
    ↓
[Vercel - Frontend]
    ↓
[Railway/Render - Backend API]
    ↓
[PlanetScale - MySQL]
    ↓
[Stripe API | Gemini API]
```


---

**Nota:** Esta es una guía básica. Cada plataforma tiene características específicas que puedes explorar para optimizar tu despliegue.
