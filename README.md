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