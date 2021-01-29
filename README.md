# Docker Compose WordPress

Este repositorio enseña como crear facilmente un WordPress con *Docker Compose*. Realmente es algo sencillo y es muy util ya sea para desarrollo. Por ejemplo, si desarrollas para WordPress y quieres tener un entorno local en el que hacer pruebas pero no quieres instalar un web server esto es muy util. También puede ser muy util para probar on componente o tema en distintas versiones.



## Instalar Docker Compose

Docker compose es una herramienta que permite gestionar multiples contenedores de docker de forma simultanea. Es capaz de crear, arrancar, para, borrar multiples con un solo comando y un fichero de configuración Yaml (docker-compose.yml).

Esta utilidad se puede instalar desde la utilidad de Python para realizar instalación de paquetes, pip, ejecutando:

pip install docker-compose

Si no tienes esta utilidad instalada, puedes consultar métodos alternativos de instalación en:

https://docs.docker.com/compose/gettingstarted/



## Descargar el repositorio

Para descargar el repositorio tenemos que ejecutar el comando:

<pre>
git clone https://github.com/AprendeIT/docker-compose-wp.git
</pre>


## Levantar los contenedores
Para levantar los contenedores debes situarte dentro del directorio donde has descargado el repositorio con <code>cd docker-compose-wp</code> y ejecutar <code>docker-compose up -d</code>
<pre>
[ger-pc docker-compose-wp]# docker-compose up -d
Building with native build. Learn about native build in Compose here: https://docs.docker.com/go/compose-native-build/
Creating network "docker-compose-wp_default" with the default driver
Creating db ... done
Creating wordpress ... done
[ger-pc docker-compose-wp]#
</pre>



## Ver estado de los contenedores

<pre>
[ger-pc docker-compose-wp]# docker-compose ps
  Name                 Command               State          Ports       
------------------------------------------------------------------------
db          docker-entrypoint.sh mysqld      Up      3306/tcp, 33060/tcp
wordpress   docker-entrypoint.sh apach ...   Up      0.0.0.0:80->80/tcp 
[ger-pc docker-compose-wp]# 
</pre>

## Parar los contenedores

<pre>
[ger-pc docker-compose-wp]# docker-compose stop
Stopping wordpress ... done
Stopping db        ... done
[ger-pc docker-compose-wp]# 
</pre>

## Eliminar los contenedores

Los datos generados en los puntos de montaje de los volumenes seguiran exitiendo.
<pre>
[ger-pc docker-compose-wp]# docker-compose rm
Going to remove wordpress, db
Are you sure? [yN] y
Removing wordpress ... done
Removing db        ... done
[ger-pc docker-compose-wp]# 
</pre>