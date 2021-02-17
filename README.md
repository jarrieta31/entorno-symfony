# Symfony 5 docker containers

## Estructura de directorios

El código fuente del proyecto symfony se encuentra en /docker-symfony/src.
Y todo lo relacionado con los contenedores docker está en /docker-symfony/docker.

## Iniciando los contenedores

El comando para iniciar los contendores debe ejecutarse estando posicionado 
en la carpeta docker.
Una vez ahí ejecutar el siguiente comando para iniciar los contenedores:

~~~shell
    docker-compose up -d
~~~

Nota: si es la primera vez que se ejecuta docker va a descargar todo lo 
necesario para iniciarse por lo que puede tardar uns minutos.

## Detener todos los contenedores

Siempre estando en el directorio docker.

~~~shell
    docker-compose stop
~~~

## Correr comandos symfony

Para correr los comandos symfony primero se debe ingresar al contendor php,
para ello ejecutar el siguiente comando:

~~~dokcer
    docker exec -ti docker_php-fpm_1 /bin/sh
~~~

Esto nos brinda una terminal dentro del proyecto, donde podrémos ejecutar todos
las órdenes de symfony, como crear contraladores etc.
Para salir solo ejecutar:
~~~shell
    exit
~~~

## Trabajar con la base de datos

Podemos utilizar un cliente de base de datos para trabjar. En mi caso utilisé
dbeaver, el cual nos permite conectar con diferentes tipos de bases de datos.
En este caso, estamos utilizando mariadb.
El puerto que utiliza la bd es 3306 y si quires saber su IP puedes usar este comando:

~~~shell
    docker inspect docker_database_1 |grep IPAddress
~~~
