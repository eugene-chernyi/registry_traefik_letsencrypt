### Quick start guide

1. Update variables in the .env file
```
  vim .env
```
2. Сhange the access mode of acme.json:
```
  chmod 600 acme.json
```
3. Run docker-compose
```
  docker-compose up -d
```

#### Options
If you want to disable web dashboard set ``` api.dashboard=false ```
If you want to disable traefik webdashboard basic authentication delete/comment lines:
```
  - "traefik.http.routers.traefik.middlewares=admin"
  - "traefik.http.middlewares.admin.basicauth.users=${TRAEFIK_ADMIN}:${TRAEFIK_ADMIN_PASSWORD}"
```
If you want to disable registry basic authentication delete/comment  lines:
```
  - "traefik.http.routers.registry.middlewares=auth"
  - "traefik.http.middlewares.auth.basicauth.users=${REGISTRY_USER}:${REGISTRY_PASSWORD}"
```
