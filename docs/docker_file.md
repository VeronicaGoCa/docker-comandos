# 🐳 Comandos para archivos Docker file
---
## 1️⃣ Imagen

### Crear una imagen
```
docker built -t nombre_contenedor .
```
### Versionando
```
docker built -t nombre_contenedor:version .
```
### Contruir imagen para subir al docker Hub
```
 docker build -t userver/cron-ticker:1.0.0 .
```
### Subir imagen a Docker Hub
```
docker login
```
Ingresar al siguiente enlace y poner en el formulario el code de confirmacion generado por el comadno docker login
```
https://login.docker.com/activate
```
```
docker container run imagen
```
