# WAHA Plus - WhatsApp HTTP API

## Deploy en Coolify

### Configuración WAHA Plus

Para usar **WAHA Plus**, necesitas:

1. **WAHA Plus Key**: Tu ключ из https://portal.devlike.pro/

2. **Docker Hub Login**: Debes hacer login antes de descargar la imagen:

```bash
docker login -u devlikeapro -p {WAHA_PLUS_KEY}
docker pull devlikeapro/waha-plus
docker logout
```

### En Coolify

1. **Nuevo recurso** → Docker Compose
2. Sube los archivos de `coolify/`
3. Configura el secreto `WAHA_PLUS_KEY` en Coolify
4. El **Environment File** debe ser `coolify/coolify.env`

### Variables importantes

| Variable | Descripción |
|----------|-------------|
| `WAHA_API_KEY` | API key para autenticación |
| `WAHA_DASHBOARD_PASSWORD` | Contraseña del dashboard |
| `WAHA_PLUS_KEY` | Tu key de WAHA Plus (secret) |

### URLs
- Dashboard: `http://IP:3000/dashboard`
- Swagger: `http://IP:3000/swagger`

### Verifica funcionamiento

```bash
curl -H "X-Api-Key: a1b2c3d4e5f6a1b2c3d4e5f6a1b2c3d4" http://TU_IP:3000/api/server/status
```
