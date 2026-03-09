# 🐳 Gestión completa de Docker: contenedores, imágenes, volúmenes y redes

Guía práctica con todos los comandos esenciales para trabajar con **Docker**.

---

## 1️⃣ Contenedores

### Ver contenedores activos
```
docker ps
```

### Ver todos los contenedores
```
docker ps -a
```

### Crear y ejecutar un contenedor
```
docker run -d --name mi_contenedor nginx
```

### Detener un contenedor
```
docker stop mi_contenedor
```

### Eliminar un contenedor
```
docker rm mi_contenedor
```

### Eliminar todos los contenedores
```
docker rm -f $(docker ps -aq)
```

---

## 2️⃣ Imágenes

### Ver imágenes
```
docker images
```

### Descargar una imagen
```
docker pull nginx:latest
```

### Crear una imagen desde Dockerfile
```
docker build -t mi_imagen .
```

### Eliminar una imagen
```
docker rmi mi_imagen
```

### Eliminar todas las imágenes no usadas
```
docker image prune -a
```

---

## 3️⃣ Volúmenes

### Ver volúmenes
```
docker volume ls
```

### Crear un volumen
```
docker volume create mi_volumen
```

### Eliminar un volumen
```
docker volume rm mi_volumen
```

### Eliminar todos los volúmenes no usados
```
docker volume prune
```

---

## 4️⃣ Redes

### Ver redes
```
docker network ls
```

### Crear una red
```
docker network create mi_red
```

### Conectar contenedor a una red
```
docker network connect mi_red mi_contenedor
```

### Desconectar contenedor de una red
```
docker network disconnect mi_red mi_contenedor
```

### Eliminar red
```
docker network rm mi_red
```

### Eliminar redes no usadas
```
docker network prune
```

---

## 5️⃣ Limpiar todo Docker

```
# Contenedores detenidos
docker container prune

# Imágenes no usadas
docker image prune -a

# Volúmenes no usados
docker volume prune

# Redes no usadas
docker network prune

# Limpieza completa
docker system prune -a --volumes
```

---

## 6️⃣ Consejos prácticos

- Siempre revisa los contenedores activos antes de eliminarlos:
```
docker ps
```
- Usa nombres claros para contenedores, imágenes, volúmenes y redes.
- Mantén los comandos de limpieza en tu documentación para no olvidar pasos importantes.

