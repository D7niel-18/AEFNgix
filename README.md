# PoC de Infraestructura

Despliegue de Aplicaciones Web · 2º DAW · Campus Cámara Comercio Sevilla

## Qué hay en el proyecto

```
nginx-static-poc/
├── docs/
│   ├── img/ --> Wireframes
├── html/
│   ├── css/styles.css      → el diseño (colores, letras)
│   └── index.html         → la página web
├── .dockerignore          → lista de archivos que no se añaden
├── docker-compose.yml     → configuración para iniciar docker
└── Dockerfile             → instrucciones para iniciar docker
```


## Cómo llega una visita a la web

```
Navegador ──► Mi ordenador, puerto 8080 ──►  (Docker), puerto 80 (Nginx)
                                              ├─ Web: carpeta html (solo se puede leer)
                                              ├─ Reglas: default.conf (solo se puede leer)
                                              └─ Registros (logs) ► se ven con docker compose logs
```

Explicado: cuando escribes `localhost:8080` en el navegador, tu ordenador manda
la petición y Nginx responde con la web.

## Comandos 

```bash
docker compose up -d                 # arrancar (en segundo plano)
docker compose ps                    # ver si está funcionando
curl -I http://localhost:8080        # pedir solo los "datos de cabecera" de la web
docker compose logs -f web           # ver el diario de lo que pasa, en directo
docker compose down                  # apagar y borrar
```
## Qué necesito para usarlo

Windows 11, Docker Desktop, VS Code y Git.