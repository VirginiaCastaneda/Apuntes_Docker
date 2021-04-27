

# -----------Voluemenes---------------
## 1. Con la misma img de python crear un contenedor con un voluemen conectado

- ---VOLUMENES: Son directorios de nuestro host conectados a un contenedor.
### ---Hay dos tipos:
- 1.Volumenes de punto de montaje: son carpetas o directorios que compartimos directamente de nuestro host a un contenedor.(reciben una ruta)
- docker run -i -t --name pygen17 -v c:/Users/virginia/Documents/Hackademy/Contenedores/HolaMundo:/home/appuser/holamundo2 virginiacp11/python-16gen:1.0.0
- holamundo2: es el nombre del volumen
- Son para entornos de desarollo, no tener que estar copiando 

- 2.Volumenes nombrados: directorios manejados internamente por docker.
- pertence a root:  Son carpetas manejadas por docker, se montan con permisos de root (nombre del volumen)
- se montan con permisos de root
- docker run -i -t --name pygen17 -v pythondata:/home/appuser/pydata virginiacp11/python-16gen:1.0.0

# 2. Crear un nuevo contenedor para hacer los volumenes.
- VAMOS A CREAR VOLUMENES DE PUNTO DE MONTAJE:
- COMPARTIR UNA CARPETA A MI CONTENEDOR.

# --------Comando para crear volumen-----
- docker run -i -t --name pygen17 -v (ruta): (Donde Montar el contenedor) -v (nombre_volumen): (ruta) nombre_imagen_creada:1.0.0

- (ruta): del directorio(carpeta holamundo) que quiero compartir con el contenedor.
- (DondeMontar el contenedor): La carpeta, puede no existir en el contenedor, en caso de que no exista se es accecible
- (nombre_volumen)---> carpeta administrado por docker

## Ejemplo:
- docker run -i -t --name pygen17 -v c:/Users/virginia/Documents/Hackademy/Contenedores/HolaMundo:/home/appuser/holamundo2 -v pythondata:/home/appuser/pydata virginiacp11/python-16gen:1.0.0
- SE CREO LOS DOS TIPOS DE VOLUMEN
- Se crea con exito

# 3. buscar la carpeta compartida en el contenedor: ls -l
- El directorio HolaMundo tiene permisos del appuser porque es volumen de montaje
- EL pydata tiene permisos de root root

# 4.CUANDO CREAS EL VOLUMEN DE MONTAJE VAS A PODER MODIFICAR EL ARCHIVO Y LOS CAMBIOS SE APLICAN INSTANTANEAMENTE,porque es una carperta compartida.
- Sirve para trabajar con lenjuajes, sin tenerlos que instalar, y trabajar desde tu editor de texto y probarlo desde el contenedor.

- -Si agrego archivos nuevos a mi carpeta compartida se agregan automaticamente al contenedor.

- Instalar en el contenedor django y otros ejemplo, en el requirements va la config.
- Comandos: pip install -r requirements.txt   

- -Si dice que django no tiene camino ejecutar esto:
- export PATH=$PATH:/home/appuser/.local/bin
- -- ya instaldo ejecutar:
- django-admin

- --Puedes instalar diferentes paquetes, 
- -Es un ambiente aislado.

# 5. Otra forma de conectar al contenedor:
- con permisos de root en caso de que no tenga:
- docker exec -ti -u 0 pygen17/bin/bash

- -u : ejecuatar el proceso con exec de cierto usuario 
- 0: pertenece a root
- root@d44adf7cc4c4:/home/appuser#
- Ya podras modificar o instalar
- --ejecuatar un apt update
- ir a :
- cd /home/appuser/
- ---Puedes cambiar el owner ship de un directorio
- chown -R appuser:appuser pydata/

- ls -l:
- ya petenece a  appuser appuser 4096 Apr 25 02:29 pydata
- --CREAR UN ARCHIVO
- COMO SE CAMBIO LOS PERMISOS 

# 6. como eliminar el contenedor:
- docker rm pygen16.

# 7. listar los volumenes
- docker volumen ls

- los archivos que no estan en un volumen se van, si se borran los contenedores.













