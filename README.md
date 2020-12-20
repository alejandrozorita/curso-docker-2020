# curso-docker-2020


## Comandos

### Container

- PS -> listado contenedores
  - -a -> Listado contenedores parados
  - -aq listado IDs containers
- inspect 'id/name' -> info del contenedor
- rename 'old-name' 'new-name'
- run 'noombre-img'
  - --name 'name--container' 'name-img' -> ejecuta la imagen con el nombre del conenedor dado
  - 'name' -it -> hacemos que el contenedor sea interactivo y podamos operar en su consola
  - 'name' 
  - d -> nos devuelve el control del terminal, no nos mustra los outputs y mantiene activo el container. EJ: docker run -d --name server-ng nginx
  - p -> expone un puerto del contenedor a la máquina. EJ : docker run -d --name server-ngx -p 8080:80 nginx
  - v -> indicamos donde queremos generar un volumen para persistir los datos. ## EJ: docker run --name db -d -v /Users/alejandro/Dev/Platzi/Servidores/Docker/fundamentos-docker-2018/mongodata:/data/db mongo 
- rm 'id' -> borra el contenedor dado
  - -rm $(docker ps -aq) -> combinamos comandos, retornamos un listado de IDs que usamos para borrar en bloque
  - -f borra el contenedor aunque este corriendo (forze)
- exit -> salimos del contenedor.
- exec -it 'nombre-container' 'comando -> ej exct -it contenedor bash, con esto entraríamos al bash del container.
- kill 'name-container' -> desde fuera del contenedor, podemos matar un contenedor
- --mount src=volu,des=/data/ -> Sirve para montar un volumen a un contenedor


### Docker volumes

- volume -> Comando principal
  - ls ->  Muestra los volumenes de Docker
  - prune -> Borra, limpia, los contenedores que no están en uso por ningún contenedor
  - create 'nombre' -> crea volumen 



### Imágenes

Una imagen está contenida de layers o capas que se van montando. 

Esto funciona como git, cada capa es una modificación sobre la anterior

- Docker pull 'nombreImagen' -> Se descarga una imagen

- Image -> comando principal
  - ls -> lista las imágenes




Cuando ejecutamos un comando en la creación de un contenedor, le establece el PID 1, si ese PID se finalizase, el contenedor se pararía


cat /etc/lsb-release  -> ver versión linux

uname -a -> obtenemos el nombre de la máquina

