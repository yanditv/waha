# WAHA - WhatsApp HTTP API

## Deploy en Coolify

### 1. Crear nuevo recurso
- Selecciona **Docker Compose** como tipo de recurso

### 2. Configuración
- **Repository**: Repo de tu proyecto o usa los archivos locales
- **Branch**: main
- **Build Pack**: Docker Compose

### 3. Docker Compose
Copia el contenido de `coolify/docker-compose.yaml`

### 4. Variables de entorno
Copia `coolify/.env.example` y configura:
- `WAHA_DASHBOARD_PASSWORD` - contraseña segura para dashboard
- `WAHA_API_KEY` - API key larga y aleatoria

### 5. Puertos
- Expón el puerto `3000`

### 6. Volúmenes persistentes
- `/app/.sessions` → `waha_sessions`

## Post-instalación

### Generar credenciales seguras
```bash
docker run --rm -v "$(pwd)/stack.env":/app/env devlikeapro/waha init-waha /app/env
```

O desde Coolify, ejecuta el comando en la terminal del contenedor.

## URLs
- Dashboard: `http://IP:3000/dashboard`
- Swagger: `http://IP:3000/swagger`
