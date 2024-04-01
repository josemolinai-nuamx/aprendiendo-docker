# Aprendiendo Docker

## Comando básicos
__Descargar una imagen__ 
```sh
# docker pull IMAGE_NAME
docker pull postgres

# docker pull IMAGE_NAME:TAG
docker pull postgres:16.2
``` 
---
__Ejecutar un contendor__ rediriengo el puerto 8080 de la máquina host al puerto 80 del contenedor
```sh
# docker -d -p <puerto_host>:<puerto_contenedor> [IMAGE_NAME/IMAGE_NAME:TAG]
docker run -d -p 8080:80  --name proxy-example nginx
``` 
__-d__ Permite ejecutar el contenedor desenlazado de la consola donde se ejecutó el comando.  
__-p 8080:80__ Mapea el puerto 8080 de la máquina host con el puerto 80 del contenedor.  
__--name proxy-example__ Permite darle un nombre al contenedor.  

---
__Mostrar un listado de los contenedores__ corriendo en la máquina host.  
```sh
# Alias o pseudónimos:
# docker container ls, docker container list, docker container ps, docker ps
docker container ls
``` 
---
__Mostrar todos los contenedores__ en la máquina host.  
```sh
docker container ls -a
``` 
__-a__ Permite listar los contenedores que esten ejecutándose o no en la máquina host.  

---
__Detener un contenedor y volver a iniciarlo__
```sh
# docker container stop [CONTAINER_NAME/CONTAINER_ID]
docker container stop proxy-example
docker container stop 9e6889d78182

# docker container start [CONTAINER_NAME/CONTAINER_ID]
docker container start proxy-example
docker container start 9e6889d78182
``` 

---
__Detener un contenedor y eliminarlo__
```sh
# docker container stop [CONTAINER_NAME/CONTAINER_ID]
docker container stop proxy-example
docker container stop 9e6889d78182

# docker container rm [CONTAINER_NAME/CONTAINER_ID]
docker container rm proxy-example
docker container rm 9e6889d78182
``` 

---
__Detener un contenedor y eliminarlo de forma forzada__
```sh
# docker container  rm -f [CONTAINER_NAME/CONTAINER_ID]
docker container rm -f proxy-example
docker container rm -f 9e6889d78182
``` 
---
__Mostrar un listado de la todas las imágenes__
```sh
docker images
```
---
__Eliminar una imagen específica__
```sh
#docker image rm [IMAGE_NAME/IMAGE_NAME:TAG/IMAGE_ID]
docker image rm postgres
docker image rm postgres:16.2
docker image rm b9390dd1ea18
```  
---
__Eliminar imágenes no usadas__
```sh
docker image prune -a
```  
