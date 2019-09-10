# Tutorial de introducción microservervicios distribuidos con Hydra

## Requerimientos
* Redis
* NPM

## Instalación de Redis ( Ubuntu 18.04 )

```
sudo apt update
sudo apt install redis-server
```

Para otros OS https://www.hydramicroservice.com/docs/quick-start/step1.html

## Hydra Router

### Adquirir copia del proyecto

```
git clone https://github.com/flywheelsports/hydra-router

```

### Configurar la conexión con Redis

```
cd hydra-router
cp config/sample-config.json config/config.json
```

### Configurar la instancia de hydra-router

```
vi config/config.json
```

Por omision, hydra intentará conectarse al servidor `host`, bien podria definirse la ip correspondiente al servidor o actualizar el archivo de configuración por el servidor correspondiente actualizando el archivo config/config.json

Si se desea iniciar la instancia en el puerto 80, se deberá contar con permisos de root, de lo contrario actualizar la entrada `servicePort` en el archivo de configuración

### Iniciar instancia de Hydra Router

```
npm install
npm start
```

### Demo

Abrir un navegador en la ruta `http://host:port` remplazando host y port por los definidos en `config.json`

## Hello world

### Prerequisitos
Para facilitar la generación del código base de un microservicio es necesario contar con Yeoman y el respectivo generador de Hydra

```
sudo npm install -g yo generator-fwsp-hydra
```

### Generación de código base
El generador es un comando iteractivo que después de responder algunas preguntas generará el proyecto correspondiente

```
yo fwsp-hydra
```

Ejecutar instancia
```
cd example
npm install
npm start
```

### TL;DR Demo
Se probar el microservicio "hello-world" sin tener que crear un proyecto desde cero

```
git clone https://github.com/emirhg/hydra-microservice-hello-world.git
cd hydra-microservice-hello-world
npm install
npm start
```

Si Hydra router se encuntra en ejecución, será posible acceder al microservicio mediante la ruta http://host:port/hello-world-service/v1/hello-world de lo contrario, por omisión el microservicio eligirá un puerto al azar el cuál es reportado en la consola al momento de ejcución y la ruta del microservicio será http://serviceIp:servicePort/v1/hello-world


## Hydra-cli ( opcional )
Conjunto de utilerias para monitorear los servicios en ejecución

Instalación
```
sudo npm install -g hydra-cli
```

Hydra no elimina las instancias detenidas por razones de debug, para realizar una limpieza de las mismas se debe actualizar los estados de los microservicios.
```
hydra-cli refresh
```

# Para más documentación sobre Hydra

https://www.hydramicroservice.com/