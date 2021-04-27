# 2. Crear el contenedor con la imagen creada anterior
- docker run -i -t --name pygen16 virginiacp11/python-16gen:1.0.0
- pygen16: es el nombre del contenedor

# 3. Ver todos los contenedores que se esten ejecutando o no.
- docker ps -a
- --Debe aparecer con el nombre: pygen16

# 4.Correr el contenedor en caso de haber salido:
- docker start -a -i pygen16

# 5.Correr python ejemplo con un mini programa
- python OperacionesBasicas.py

# 6.Ejecutar el contenedor que tu decides una vez que haya sido detenido
- docker start -a -i beautiful_khayyam (es el nombre aleatorio o el que tu estaableciste) 

- Los contenedores pueden borrarse y se desasen las configuaraciones, pero si los vuelvo
- a ejecuatar lo genera igual.

