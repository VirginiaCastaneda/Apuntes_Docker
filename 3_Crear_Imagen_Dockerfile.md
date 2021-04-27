# 1. Crear la imagen del contenedor con el Dockerfile.
- --Configurar el Dockerfile a tus necesidades
- --Posicionarte en la carperta que esta el Dockerfile
## Ejecuatar
- docker build -t virginiacp11/python-16gen:1.0.0 -t virginiacp11/python-16gen:lastest .

- .(punto) -----> hace referencia al directorio de contexto, para no poner toda la ruta del archivo, el punto simplicfica eso. Solo si estas en el directorio de contexto
- build ---> construir una imagen de docker con base en un Dockerfile
- -t ----> especificar el nombre de la imagen base


## Verificar la imagen
- docker images

## Subir la imagen 
- docker push virginiacp11/python-16gen:tagname
- docker push virginiacp11/python-16gen:1.0.0
- --Ver los archivos:ls

# Cambios?
- --si hay cambios en el dockerfile o en la app crear un commit: 
- --Guardar una nueva version con los cambios crear una nueva imagen.
- docker commit -m "nueva version 2.0" pygen16 virginiacp11/python-16gen:2.0
### Nuevo contenedor
- --Crear un nuevo contenedor con la img 2.0
- docker run -i -t --name pygen16 virginiacp11/python-16gen:2.0

### --subir la imagen 
- docker push virginiacp11/python-16gen:2.0

# Como se crea la imagen (pasos)
- Pasos (capas)
1. Que imagen base va a utilizar
2. Expose el puerto
3. Definir la variaable de entorno.
4. otra variable de entorno
5. crear el grupo y el usuario
6. Ejecutar el apt install y el nano
7. Copiar la archivo o app
8. Definir el uusario que va a ejecuatar 
9. definir el workdir
10. ejecutar el CMD

- Si sale bien te da el id del docker
