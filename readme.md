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
```sh
sudo docker container start --attach -i dam_alp1	# iniciar y acceder al contenedor
ip a							# comprobar ip
ping google.com						# hacer ping
```
### Crea un contenedor con el nombre 'dam_alp2'. ¿Puedes hacer ping entre los contenedores?
```sh
sudo docker container start --attach -i dam_alp1 		# acceder al contenedor dam_alp1
```
y en otra terminal
```sh
sudo docker container create -i -t --name dam_alp2 alpine	# crear contenedor dam_alp2
sudo docker container start --attach -i dam_alp2 		# acceder al contenedor dam_alp2
```
y ahora tenemos que ejecutar en los 2 contenedores:
```sh
ip a			# comprobar ip
ping 172.17.0.2		# hacer ping a el otro contenedor
```
### Sal del terminal, ¿que ocurrió con el contenedor?
Control + d: Se detiene el contenedor

Cerrar terminal: Se sigue ejecutando en el fondo
### ¿Cuanta memoria en el disco duro ocupaste?
```sh
sudo docker system df -v	# comprobar el espacio en disco que ocupan las imagenes y contenedores
```
Los contenedores pesan unos cuantos bytes, practicamente nada y la imagen de alpine unos 7.8MB, aunque tenga 2 contenedores solo necesito una imagen de alpine
### ¿Cuanta RAM ocupan los contenedores? ¿Hay algún comando docker para saber esto?.
```sh
sudo docker stats 		# comprobar uso de cpu, ram, nombre, red, disco, etc. de cada contenedor
```
Cada contenedor consume 512KiB de memoria RAM
