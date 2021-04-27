
# iniciar el contenedor
- docker start -a -i name_contendor

- --Persistencia: con los volumnes
- volumenes: directorios del host o conectados = Persistencia


# Dos tipos de contendores:
- --Voluemens de punto de montaje: compartir informacion
- --Volumenes nombrados: directorios manejados internamente por docker.
- pertence a root:
- --Son carpetas manejadas por docker, se montan con permisos de root

### Volumenes podemos compartir carpetas

- --Directorio que quiero compartir con mi contenedor
- docker run -i -t ---name pygen16 -v ruta_completa repositorio_img:2.0

- --Crear un entorno de desarollo 
- --Para no instalar varias versiones de cierto lenguaje.
- --las pruebas se haran en un ambiente linux
- --Crear un contenedor con el programa que trae
