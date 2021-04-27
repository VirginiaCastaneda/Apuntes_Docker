
# --------Docker-compose------------
- mediante archivos YAML para poder instruir al Docker Engine a realizar tareas, programaticamente.

- Ejecutar uno o mas contenedores y poder administrarlos
- Se le puede considerar un mini orquestrador.
- Da flexibilidad

### Si ya tengo un contendor creado y creo un volumen no puedo conectar a ese contenedor
- tengo que crear otro contenedor y especificar en su creacion que va a estar conectado a un volumen.
# Que es? 
1. Empezar, se usara un archivo de texto plano para definir los contenedores que se usaran
- Stack: serie de contendores conectados o administarados en un mismo archivo.
- Tiene su sintaxis.
- YML: se manejan por identacion 

# Estructura
- Ejemplo:
- version:'3.4' //Empiezan por la version
- services: //a los contenedores se les conoce como servicios
- web: //nombre que queramos llamar al contenedor
- image:la imagen del contenedor: 
- Ports: // se definen los puertos.
- tty: true //corresponde al parametro -t: que es ejecuatar una terminal
- stdin-open:true //parametro -i: mantiene una entrada abierta
- volumes:
- Dependiendo el tipo de volumen
- c:ruta_carpeta_a compartir:/home/appuser/holamundo //voluemens de punto de montaje
- pydata:/home/appuser/data  //volumen name

- //Se define otro contenedor
- db:
- image:
- ports:
- restart: unless-stopped // indica que siempre se reinicia a menos que yo manualmente lo detenga.
  	- environment: //se definen las varibales de entorno
            - POSTGRES_PASSWORD=p4ssw0rd
            - POSTGRES_USER=adminb
            - PGDATA=/var/lib/postgressql/data/PGDATA // en un volumen guarde la inf 
        - volumes: 
            - pgdata:/var/lib/postgressql/data/pgdata
- volumes: 
    - pydata: ro //contenedores van a ser de solo lectura.
    - pgdata:
## -----------------------------------------------------------------------------

## //Contenedor para back, front, bd para la app en un solo archivo, seria un stack para el ambiente de desarollo, los conecta en una red interna de docker, 

# 1. UNA VEZ DEFINIDO EL DOCKER-COMPOSE DE PASA A EJECUTAR
- -Posicionarte en la carpeta donde esta el docker compose
- 2. docker-compose up -d ----> los va acrear y ejecutar los archivos.
- 3. docker container ls : lista los contenedores que se estan ejecutando
- docker ps ls

- 4. Como interactuar con el contenedor de web el de python
- docker-compose exec web /bin/bash o
- docker start -a -i contenedores_web_1


- 5. cambiar los parametros a root
- docker-compose exec -u root web /bin/bash

- docker exec -ti -u 0 contenedores_web_1 /bin/bash
- --despues
- chown -R appuser:appuser pydata

- -ya puedes crear archivos en el pydata

# Detener todos los contenedores
- docker-compose stop

- docker-compose down los detiene y los borra, pero no borra los volumenes

- docker-compose down 



	
