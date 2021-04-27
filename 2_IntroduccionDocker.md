# Docker introdución

# 1. Ejecutar la version
- docker --version

# 2. Crear un contenedor y ejecutarlo
- docker run hello-word

- -->Los contenedores tienen etiquetas, que tambien vendrian siendo las distintas versiones de la solucion.

- imagenes ---> pueden ser creadas o descargar de hub docker
- son planos del contenedor.
- Se pueden construir n num de contenedores

- etiqueta que genera docker: 
- latest ---> en entornos de producion no es recomendable, porque apunta a la ultima version.
- Actualiza la version.

## ----Nuevo contenedor----
- docker run [options] IMAGE [COMMAND] [ARG ...]

# 3. Crear un contenedor en ubuntu
- docker run -i -t ubuntu bash

- ubuntu --->imagen
- bash --->comando ---->interprete que quiero queejecute el  contenedor
- -i ---> interativo: interactuar con el contendor
- -t ---> crea una terminal virtual para poder interactuar con bash
- exit ---> salir del contenedor
- se ejecuta un entorno de bash 

- apt update ----> actualizar

- --Se ejecuta en un entorno aislado.
- apt install nano ---> instalar nano


### ---Cada que ejecuto un docker run me ejecuta otro contenedor, con un root y un usuario y su numero.

# 4 Ver contenedores 
- docker ps ---> que contenedores se esta ejecutando
- id ---> es unico

- Ver todos los contenedores que se esten ejecutando o no.
- docker ps -a


# 5. Ejecutar contenedor una vez detenido

- ejecutar el contenedor que tu decides una vez que haya sido detenido
- docker start -a -i beautiful_khayyam (es el nombre aleatorio o tu lo defines)
- docker start -a -i exciting_lalande

- cada contenedor tiene  su propio
- almacenamiento aislado: Puedes tener dos contendores iguales, pero cada uno con aislados.
- touch name ---> crea un nuevo archivo.