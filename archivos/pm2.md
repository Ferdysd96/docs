## PM2

## Instalar

```bash
$ npm i -g pm2
```

## INICIAR 

```bash
# Iniciar proyecto
$ pm2 start nameProject/index.js

#Iniciar todos los proyectos
$ pm2 start all

#Iniciar el proyecto con los siguientes flags
$ pm2 start nameProject/index.js  --aqui uno de los flags de abajo
   --watch: ver cambios,
   --name myname: asig nombre, 
```

## REINICIAR Y SUBIR

```bash
#Aqui cuando el servidor se apaga o reinica 
#se auto ejecuta el proyecto

# solo linux
$ pm2 startup 

# Quitar solo linux
$ pm2 unstartup

# windows
$ pm2 ecosystem 
$ pm2 start ecosystem.config.js
```

## LISTAR

```bash
#Ver un listado de proyetos
$ pm2 ls
```

## Reiniciar

```bash
# Reiniciar por archivo, id o nombre
$ pm2 restart nameProject/index.js 

#Reiniciar todos 
$ pm2 restart all
```

## PARAR

```bash
# Parar por archivo, id o nombre
$ pm2 stop nameProject/index.js 

#Parar todos los proyectos
$ pm2 stop all
```

## ELIMINAR

```bash
# Primero paramos todo
$ pm2 stop all

# Eliminamos por archivo, id o nombre
$ pm2 delete nameProject/index.js 

# Eliminiar todo
$ pm2 delete all
```

## MONITOREAR

```bash
# Monitorear en consola
pm2 monit

# Monitorear y Abre la web
$ pm2 monitor 
```

## HISTORIAL

```bash
#Ver logs
$ pm2 log
```
