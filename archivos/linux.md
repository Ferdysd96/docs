

## WEBPACK MAX WATCH

```bash
 echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p

 cat /proc/sys/fs/inotify/max_user_watches

 fs.inotify.max_user_watches=524288
```

## REPOSITRIOS / LINKS
  
  #PGADMIN4
  ```bash
  #Importar LLave
  echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" |sudo tee /etc/apt/sources.list.d/pgdg.list
  
  #Crear archivo
  $ sudo nano /etc/apt/sources.list.d/pgdg.list
  
  #Guardar
  deb http://apt.postgresql.org/pub/repos/apt/ focal-pgdg main
  
  $ sudo apt update
  $ sudo apt install pgadmin4
  ```
   #POSTGRES 12

  - https://remot-technologies.com/como-instalar-postgresql-12-ubuntu-18-04/
  
  ```bash
  #Entrar a postgres
  $ sudo -u postgres psql
  
  #Cambiar clave
  $ alter user postgres with password 'hello123';
  ```
  
  #Node
  
  - https://github.com/nodesource/distributions
