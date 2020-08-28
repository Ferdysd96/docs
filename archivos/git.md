## GIT
         
## NOMBRE USUARIO

``` bash
  # Asignar nombre
  $ git config --global user.name "Ferdys"
  
  # ver nombre
  $ git config --global user.name
``` 

## CORREO USUARIO

``` bash
  # Asignar correo
  $ git config --global user.email "ferdysd96@gmail.com"
  
  # Ver correo
  $ git config --global user.email
``` 

 ##  REMOTO
 
``` bash
 # Clonar un repositorio
 $ git clone mylink    
 
 # Conectar con nuestro repositorio
 $ git remote add origin myLink
  
  # Comprobar la conexion
 $ git remote -v  
 
 # Push para subir los commists
 $ git push -u origin myRama
 
 # Cambiar url
 $ git remote set-url origin myLink 
 
 # Forzar el push (OJO) Solo sube tus commist y borra los demas 
 $ git push origin myRama --force 
  
 # Integrar nuevos cambios
 $ git pull origin master           
``` 

## ARCHIVOS

``` bash
  # Iniciar git    
  $ git init
  
  # Estado de los archivos
  $ git status 
  
  # Agregar un archivo
  $ git add myFile 
  
  # Agregar todos los archivos
  $ git add -A
  
  # Remover archivo
  $ git rm --cached myFile      
``` 

## COMMITS

``` bash
  # Crear nuevo commit
  $ git commit -m "Initial commit"    
  
  # Logs de los commits 
  $ git log  
  
  # Viajar al commit
  $ git checkout myKey
  
  # Volverl al ultimo commit 
  $ git checkout master            
``` 

## RESETS

``` bash
  # Borra despues de ese commit y nos deja el codigo
  $ git reset -- soft myKey
  
  # Borra despues de ese commit y borra todo el codigo (OJO)
  $ git reset -- hard myKey      
 ``` 
 
## RAMAS

``` bash
  # Ver las ramas 
  $ git branch 
  
  # Crear nueva rama
  $ git branch myRama
  
  # Cambiar de rama
  $ git checkout myRama
  
   # Unir ramas
  $ git merge myRama
  
  # Borrar ramas
  $ git branch myRama -d 
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
#Establecer tiempo
git config --global credential.helper 'cache --timeout 3600'

#Ayuda
git help credential-cache
```
