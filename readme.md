### Descarga la imagen "alpine" SIN ARRANCARLA y comprueba que está en tu equipo
```sh
sudo docker image pull alpine	# descargar imagen
sudo docker image ls		# mostrar todas las imagenes instaladas
```
### Crea un contenedor sin ponerle nombre. ¿está arrancado? Obtén el nombre
```sh
sudo docker container create -i -t alpine	# crear contenedor con la imagen de alpine
sudo docker ps -a				# mostrar todos los contenedores
```
Al crear el contenedor está detenido, se puede iniciar con:
```sh
sudo docker container start <nombre contenedor>
```
### Crea un contenedor con el nombre 'dam_alp1'. ¿Como puedes acceder a él?
```sh
sudo docker container create -i -t --name dam_alp1 alpine 	# crear contenedor con el nombre dam_alp1
sudo docker container start --attach -i dam_alp1		# iniciar y acceder al contenedor
```
### Comprueba que ip tiene y si puedes hacer un ping a google.com

### Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?

### Sal del terminal, ¿que ocurrió con el contenedor?

### ¿Cuanta memoria en el disco duro ocupaste?

### ¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?.
