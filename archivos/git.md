## GIT
         
## NOMBRE USUARIO

``` bash
  # Asignar nombre
  $ git config --global user.name "your-name"
  
  # ver nombre
  $ git config --global user.name
``` 

## CORREO USUARIO

``` bash
  # Asignar correo
  $ git config --global user.email "youremail@gmail.com"
  
  # Ver correo
  $ git config --global user.email
``` 

 ##  REMOTO
 
``` bash
 # Clonar un repositorio
 $ git clone repository-link.com    
 
 # Conectar con nuestro repositorio
 $ git remote add origin repository-link.com   
  
  # Comprobar la conexion
 $ git remote -v  
 
 # Push para subir los commits
 $ git push -u origin new-branch
 $ git push
 
 # Cambiar url
 $ git remote set-url origin repository-link.com 
 
 # Forzar el push (OJO) Solo sube tus commist y borra los demas 
 $ git push origin new-branch --force 
 $ git push -f
  
 # Integrar nuevos cambios
 $ git pull origin master --rebase
 $ git pull --rebase
 
 #Borrar rama remota 
 git push -d origin new-branch
``` 

## ARCHIVOS

``` bash
  # Iniciar git    
  $ git init
  
  # Estado de los archivos
  $ git status 
  
  # Agregar un archivo
  $ git add my-file 
  
  # Agregar todos los archivos
  $ git add -A
  $ git add .
  
  # Remover archivo
  $ git rm --cached my-file      
``` 

## COMMITS

``` bash
  # Crear nuevo commit
  $ git commit -m "Initial commit"    
  
  # Logs de los commits 
  $ git log  
  
  # Viajar al commit
  $ git checkout my-key
  
  # Volverl al último commit 
  $ git checkout master            
``` 

## RESETS

``` bash
  # Borra despues de ese commit y nos deja el codigo
  $ git reset -- soft my-key
  
  # Borra despues de ese commit y borra todo el codigo (OJO)
  $ git reset -- hard my-key      
 ``` 
 
## RAMAS

``` bash
  # Ver las ramas 
  $ git branch 
  
  # Crear nueva rama
  $ git branch new-branch
  
  # Cambiar de rama
  $ git checkout new-branch
  
  # Crear nueva rama y cambiar a rama creada
  $ git checkout -b new-branch
   
  # Renombrar rama actual
  $ git branch -m new-name
  
  # Agregar cambios de una rama a otra (Preferiblemente antes que el merge)
  $ git rebase master
  
  # Unir ramas
  $ git merge master
  
  # Borrar rama
  $ git branch new-branch -d 
  ``` 
  
  ## KEY SSH

``` bash
  # Crear la key
  $ ssh-keygen -t ed25519 -C "tu_correo@ejemplo.com"
   
   # Presiona Enter para aceptar la ubicación por defecto: C:\Users\TU_USUARIO\.ssh\id_ed25519
   # Puedes dejar la contraseña vacía si no quieres introducirla cada vez. (DAR ENTER)
  
  # Agregar nuestra clave SSH al SSH-Agent
  $ eval "$(ssh-agent -s)" && ssh-add ~/.ssh/id_ed25519  

  # Ver tu clave pública
  $ cat ~/.ssh/id_ed25519.pub 
  
 <!-- Ahora Debes dirigirte a github/gitlab etc y agregar con tu clave pública el ssh -->

 # Agregar tu clave publica https://bitbucket.org/account/settings/ssh-keys/

  # Probar tu conexion 
  $ ssh -T git@bitbucket.org 

  # Si anteriormente tenías configurado el repositorio usando HTTPS, actualiza la URL remota para utilizar SSH
  $ git remote set-url origin <SSH_REMOTE_URL>
 ``` 
 
 ## FIJAR CREDENCIALES (LINUX)
```bash
  # Establecer un asistente de credenciales en la configuración de git
  $ git config --global credential.helper store
  
  #Establecer tiempo
  $ git config --global credential.helper 'cache --timeout=3600'
```
