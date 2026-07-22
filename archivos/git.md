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

# Configurar una clave SSH para Bitbucket (Windows - PowerShell)

## 1. Generar una nueva clave SSH

```powershell
ssh-keygen -t ed25519 -C "tu_correo@ejemplo.com"
```

Cuando aparezca el siguiente mensaje:

```text
Enter file in which to save the key (C:\Users\TU_USUARIO\.ssh\id_ed25519):
```

Presiona **Enter** para utilizar la ubicación predeterminada.

Cuando solicite una contraseña (passphrase):

- Presiona **Enter** si no deseas utilizar una contraseña.
- O escribe una contraseña para mayor seguridad.

---

## 2. Iniciar el servicio SSH Agent

> **Importante:** Ejecuta PowerShell como **Administrador**.

Configura el servicio para que inicie automáticamente y luego inícialo:

```powershell
Set-Service -Name ssh-agent -StartupType Automatic
Start-Service ssh-agent
```

> Si el servicio ya está iniciado, puedes omitir este paso.

---

## 3. Agregar la clave al SSH Agent

```powershell
ssh-add "$env:USERPROFILE\.ssh\id_ed25519"
```

Verifica que la clave fue agregada correctamente:

```powershell
ssh-add -l
```

---

## 4. Mostrar la clave pública

```powershell
Get-Content "$env:USERPROFILE\.ssh\id_ed25519.pub"
```

Copia todo el contenido que comienza con:

```text
ssh-ed25519 AAAA...
```

---

## 5. Agregar la clave a Bitbucket

Ingresa a:

https://bitbucket.org/account/settings/ssh-keys/

Haz clic en **Add key** y pega la clave pública copiada en el paso anterior.

---

## 6. Probar la conexión

```powershell
ssh -T git@bitbucket.org
```

La primera vez aparecerá un mensaje similar a:

```text
The authenticity of host 'bitbucket.org' can't be established.
ED25519 key fingerprint is...
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Escribe:

```text
yes
```

Si la autenticación fue exitosa, verás un mensaje similar a:

```text
authenticated via ssh key.
```

---

## 7. Cambiar el repositorio de HTTPS a SSH (si aplica)

Verifica la URL actual del repositorio:

```powershell
git remote -v
```

Si la URL comienza con `https://`, cámbiala por la URL SSH:

```powershell
git remote set-url origin git@bitbucket.org:USUARIO/REPOSITORIO.git
```

Verifica el cambio:

```powershell
git remote -v
```

Deberías ver una salida similar a:

```text
origin  git@bitbucket.org:USUARIO/REPOSITORIO.git (fetch)
origin  git@bitbucket.org:USUARIO/REPOSITORIO.git (push)
``` 
 
 ## FIJAR CREDENCIALES (LINUX)
```bash
  # Establecer un asistente de credenciales en la configuración de git
  $ git config --global credential.helper store
  
  #Establecer tiempo
  $ git config --global credential.helper 'cache --timeout=3600'
```
