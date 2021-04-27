
## 1. CREAR IMAGENES CON BASE EN EL CONTENEDOR.

- ---Crear un contendor base: basado en node.js, tu lo configuras para que todos tengan lo mismo.

### Dockerfile 
- Todo lo que queremos que tenga el contenedor
- Divido por capas

# Estructura de un Dockerfile

- FROM python:3.7.10-buster ---> el numero es la version

- EXPOSE 8000 ---> siempre definir los puertos, el contenedor va a usar el puerto 8000

- # Keeps Python from generating .pyc files in the container
- ENV PYTHONDONTWRITEBYTECODE 1 ----> defiene variable de entorno que utiliza python

- # Turns off buffering for easier container logging
- ENV PYTHONUNBUFFERED 1 ---> otra varible de entorno

- # Switching to a non-root user, please refer to https://aka.ms/vscode-docker-python-user-rights
- RUN **groupadd** --**gid** 1000 appuser(name) \    ----> ejecuta el docker 
-     && **useradd** --uid 1000 --gid 1000 --shell /bin/bash --create-home appuser

- RUN apt update && apt install **-y** libpq-dev nano -----> Sino tiene relacion con los usuarios se crea otra capa (RUN)

- USER appuser ----->le digo al contenedor que lo ejecute tal usuario.

- WORKDIR /home/appuser -----> es el home del usuario que se ejecutara

- CMD ["/bin/bash"] -----> ejecuata un entorno bash.

- **groupadd** ---> agrega un grupo
- **useradd** ---> agrega usuario.
- **gid** ---> le pone un id
- && ----> concatenar para no poner doble RUN.


- **-y** ---->no te pide que el usuario diga si o no en la instalacion.(interactivo)
- sino lo tiene si te pide que lo confirmes.(integracion continua)