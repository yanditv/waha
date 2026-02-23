# WAHA - WhatsApp HTTP API

## Deploy en Coolify

### Instalación automática

1. **Nuevo recurso** → Busca "WAHA" o selecciona **Docker Compose**

2. **Repository**: Sube estos archivos o conecta tu repo Git

3. **Branch**: main

4. **Docker Compose File**: `coolify/docker-compose.yaml`

5. **Environment File**: `coolify/coolify.env`

6. **Puerto**: 3000

### Configuración automática

Coolify detectará automáticamente:
- ✅ Puerto 3000 expuesto
- ✅ Volumen persistente `waha_sessions`
- ✅ Health check en `/api/health`
- ✅ Variables de entorno editables

### Post-install

Después del primer deploy, genera credenciales seguras:

```bash
docker exec waha init-waha /app/env
```

O accede al dashboard en `http://IP:3000/dashboard`

### URLs
- Dashboard: `http://IP:3000/dashboard`
- Swagger: `http://IP:3000/swagger`
