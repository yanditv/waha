# WAHA - WhatsApp HTTP API

## Deploy en Coolify

### Configuración en Coolify

1. **Nuevo recurso** → Docker Compose
2. **Repository**: Sube los archivos de `coolify/`
3. **Docker Compose File**: `coolify/docker-compose.yaml`
4. **Environment File**: `coolify/coolify.env`

### Variables obligatorias

Configura estas variables en Coolify (Secrets):

| Variable | Descripción |
|----------|-------------|
| `WAHA_DASHBOARD_PASSWORD` | Contraseña para dashboard |
| `WAHA_API_KEY` | API key (usa una cadena larga aleatoria) |

### Importante

- Las credenciales deben persistir entre reinicios
- NO ejecutes `init-waha` - configura las variables directamente
-生成 una API key segura: `openssl rand -hex 32`

### URLs
- Dashboard: `http://IP:3000/dashboard`
- Swagger: `http://IP:3000/swagger`

### Problemas comunes

**401 Unauthorized en health check**
→ Verifica que `WAHA_DASHBOARD_PASSWORD` y `WAHA_API_KEY` estén configurados

**Credenciales no persisten**
→ El volumen `waha_env` guarda las credenciales en `/app/env`
