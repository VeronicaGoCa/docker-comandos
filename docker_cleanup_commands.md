# 🐳 Comandos para Limpiar Docker (Contenedores, Imágenes, Volúmenes y Redes)

Guía práctica de los comandos más usados para limpiar recursos en
**Docker** cuando el disco se llena o cuando se desea reiniciar el
entorno de contenedores.

------------------------------------------------------------------------

# 1. Ver uso de espacio en Docker

``` bash
docker system df
```

Muestra el espacio usado por:

-   Imágenes
-   Contenedores
-   Volúmenes
-   Cache de compilación

------------------------------------------------------------------------

# 2. Contenedores

### Ver contenedores en ejecución

``` bash
docker ps
```

### Ver todos los contenedores

``` bash
docker ps -a
```

### Eliminar un contenedor

``` bash
docker rm nombre_contenedor
```

### Forzar eliminación

``` bash
docker rm -f nombre_contenedor
```

### Eliminar todos los contenedores

``` bash
docker rm -f $(docker ps -aq)
```

------------------------------------------------------------------------

# 3. Imágenes

### Ver imágenes

``` bash
docker images
```

### Eliminar una imagen

``` bash
docker rmi nombre_imagen
```

### Eliminar todas las imágenes

``` bash
docker rmi -f $(docker images -q)
```

### Eliminar imágenes no usadas

``` bash
docker image prune -a
```

------------------------------------------------------------------------

# 4. Volúmenes

### Ver volúmenes

``` bash
docker volume ls
```

### Eliminar un volumen

``` bash
docker volume rm nombre_volumen
```

### Eliminar todos los volúmenes

``` bash
docker volume rm $(docker volume ls -q)
```

### Eliminar volúmenes no usados

``` bash
docker volume prune
```

------------------------------------------------------------------------

# 5. Redes

### Ver redes

``` bash
docker network ls
```

### Eliminar una red

``` bash
docker network rm nombre_red
```

### Eliminar redes no utilizadas

``` bash
docker network prune
```

------------------------------------------------------------------------

# 6. Limpiar cache de compilación

``` bash
docker builder prune
```

Eliminar todo el cache:

``` bash
docker builder prune -a
```

------------------------------------------------------------------------

# 7. Limpieza general

### Eliminar contenedores detenidos, redes no usadas y cache

``` bash
docker system prune
```

### Eliminar también imágenes no usadas

``` bash
docker system prune -a
```

### Limpieza completa (incluye volúmenes)

``` bash
docker system prune -a --volumes
```

⚠️ **Advertencia:** Este comando elimina todos los recursos que no estén
en uso.

------------------------------------------------------------------------

# 8. Comandos rápidos (resumen)

``` bash
docker rm -f $(docker ps -aq)
docker rmi -f $(docker images -q)
docker volume rm $(docker volume ls -q)
docker network prune
docker system prune -a --volumes
```

------------------------------------------------------------------------

# 9. Consejo DevOps

Revisar regularmente el uso de espacio:

``` bash
docker system df
```

Esto ayuda a evitar que el sistema acumule muchos GB en imágenes,
contenedores o volúmenes no utilizados.
