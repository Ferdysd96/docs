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
 
 # Push para subir los commists
 $ git push -u origin new-branch
 $ git push
 
 # Cambiar url
 $ git remote set-url origin repository-link.com 
 
 # Forzar el push (OJO) Solo sube tus commist y borra los demas 
 $ git push origin new-branch --force 
 $ git push -f
  
 # Integrar nuevos cambios
 $ git pull origin master --rebase
 $ git pull rebase
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
  $ git checkout my-Key
  
  # Volverl al ultimo commit 
  $ git checkout master            
``` 

## RESETS

``` bash
  # Borra despues de ese commit y nos deja el codigo
  $ git reset -- soft my-Key
  
  # Borra despues de ese commit y borra todo el codigo (OJO)
  $ git reset -- hard my-Key      
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
   
  # Renombrar rama
  $ git branch -m new-name
  
  # Agregar cambios de una rama a otra (Preferiblemente antes que el merge)
  $ git rebase master
  
  # Unir ramas
  $ git merge master
  
  # Borrar ramas
  $ git branch new-branch -d 
  ``` 
  
  ## KEY SSH

``` bash
  # Crear la key
  $ ssh-keygen -t rsa -b 4096 -C your_email@example.com
  
  #Ahora te preguntara si deseas que la clave SSH se guarde en ese
  #directorio, das enter y después te pedirá contraseña,
  #es recomendable no poner para que no tengas que escribirla 
  #cada que hagas uso de esta.
  
  # Agregar nuestra clave SSH al SSH-Agent
  $ eval "$(ssh-agent -s)" && ssh-add ~/.ssh/id_rsa    
 ``` 
 
 ## FIJAR CREDENCIALES (LINUX)
```bash
  $ git config --global credential.helper store
  
  #Establecer tiempo
  $ git config --global credential.helper 'cache --timeout=3600'
```
