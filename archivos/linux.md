

## WEBPACK MAX WATCH

```bash
 echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p

 cat /proc/sys/fs/inotify/max_user_watches

 fs.inotify.max_user_watches=524288
```

## REPOSITRIOS / LINKS


 #POSTGRES 12

  - https://remot-technologies.com/como-instalar-postgresql-12-ubuntu-18-04/
  
  #PGADMIN4
  ```bash
  $ sudo nano /etc/apt/sources.list.d/pgdg.list
  
  #Guardar
  deb http://apt.postgresql.org/pub/repos/apt/ focal-pgdg main
  ```
