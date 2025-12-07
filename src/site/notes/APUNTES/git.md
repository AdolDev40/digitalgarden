---
{"dg-publish":true,"permalink":"/apuntes/git/"}
---


# git

## Instalación

Entramos en la página [Git - Downloads](https://git-scm.com/downloads)

La misma realiza el análisis en que dispositivo se debe instalar también puedes llegar a instalarlo desde un [[gestor de paquetes\|gestor de paquetes]] 

## Comandos

### Configuración inicial

- Establecer tu nombre de usuario:

```shell
git config --global user.name "nombreUsuario"
#en mi caso es "nombreUsuario"
#Sería el nombre de usuario de github
```

- Establecer tu correo electrónico:

```shell
git config --global user.email "correo"
#En mi caso es "correo"
#Sería el nombre de correo de github
```

- Verificamos la  configuración:

```shell
git config --list
```

```shell
C:\Users\roddot>git config --list
diff.astextplain.textconv=astextplain
filter.lfs.clean=git-lfs clean -- %f
filter.lfs.smudge=git-lfs smudge -- %f
filter.lfs.process=git-lfs filter-process
filter.lfs.required=true
http.sslbackend=openssl
http.sslcainfo=C:/Program Files/Git/mingw64/etc/ssl/certs/ca-bundle.crt
core.autocrlf=true
core.fscache=true
core.symlinks=false
pull.rebase=false
credential.helper=manager
credential.https://dev.azure.com.usehttppath=true
init.defaultbranch=master
user.email=correo #configuración del correo
user.name=nombreUsuario #configuración del nombre
```

### Crea y clona repositorios

- Inicializar un nuevo repositorio:

```shell
git init
#Esto lo realiza el que crea el repositorio
```

- Clonar un repositorio existente:

```shell
git clone <url_del_repositorio>
#Esto va a realizar los colaboradores
```

### Flujo de Trabajo Básico

- Ver el estado de los archivos:

```shell
git status
```

```shell
PS C:\Users\roddot\Documents\Sage Log> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   .obsidian/plugins/obsidian-linter/data.json
        modified:   .obsidian/plugins/telegram-sync/data.json
        modified:   .obsidian/workspace.json
        modified:   Notas de captura/Ingles.md
        modified:   Notas de captura/Lista de canciones en ingles.md
        modified:   "Notas de captura/Lista de compilaci\303\263n de canciones.md"
        modified:   "Notas de captura/Organizaci\303\263n de archivos.md"
        modified:   "Notas de captura/Organizaci\303\263n.md"
        modified:   Notas de captura/Python.md
        modified:   Notas de referencia/API.md
        modified:   "Notas de referencia/Administraci\303\263n del DBA.md"
        modified:   "Notas de referencia/An\303\241lisis de sistemas - Dise\303\261o y M\303\251todos de Whitten.md"
        modified:   Notas de referencia/Callout en obsidian.md
        modified:   Notas de referencia/Configurar un perfil de privacidad de firefox.md
        modified:   "Notas de referencia/Consecuencias de la falta de sue\303\261o.md"
        modified:   Notas de referencia/Controlando el acceso de los usuarios BD.md
        modified:   Notas de referencia/Diferencia entre http y https.md
        modified:   Notas de referencia/MongoDB.md
        modified:   "Notas de referencia/M\303\251todo horizontal Finanzas de empresas.md"
        modified:   Notas de referencia/Open source.md
        modified:   Notas de referencia/OpenSSL.md
        modified:   Notas de referencia/Plugin kanban de obsidian.md
        modified:   Notas de referencia/Plugin tasks de obsidian.md
        modified:   "Notas de referencia/Proyecto de lenguaje de programaci\303\263n 4.md"
        modified:   Notas de referencia/Syncthing.md
        modified:   "Notas ideas/Autenticaci\303\263n con Auth0.md"
        modified:   Notas ideas/Borrar aplicaciones con adb.md
        modified:   Notas ideas/Ciclos para pl sql.md
        modified:   Notas ideas/Condiciones IF, ELSIF, ELSE END IF.md
        modified:   "Notas ideas/Configuraci\303\263n de MongoDB para LP4.md"
        modified:   Notas ideas/Configurar un AppImage.md
        modified:   "Notas ideas/Divisi\303\263n del trabajo de lenguaje de programaci\303\263n 4 Kanban.md"
        modified:   "Notas ideas/Divisi\303\263n para el tema revisi\303\263n documental de TS Kanban.md"
        modified:   Notas ideas/Estructura de codigo del proyecto LP4.md
        modified:   "Notas ideas/Inform\303\241tica administrativa Kanban.md"
        modified:   "Notas ideas/Instalaci\303\263n de adb y fastboot.md"
        modified:   "Notas ideas/Intalaci\303\263n de yt-dlp.md"
        modified:   Notas ideas/Manejo de errores y excepciones pl_sql.md
        modified:   Notas ideas/Procedimiento en pl sql.md
        modified:   Notas ideas/Rutas, Modelos y componentes del backend de LP4.md
        modified:   Notas ideas/Uso del  %Type.md

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        "Notas ideas/Git y github para el proyecto de lenguaje de programaci\303\263n 4.md"
        Notas ideas/Plugin Git de obsidian.md

no changes added to commit (use "git add" and/or "git commit -a")
PS C:\Users\roddot\Documents\Sage Log>
```

- Añadir archivos al área de preparación (staging):Para añadir todos los archivos modificados:

```shell
git add <archivo>
```

> [!NOTE] Nota
> Agrega solo el archivo o archivos específicos que indiques. Por ejemplo:
> `git add archivo.txt`

```shell
git add .
```

> [!NOTE] Nota
> - Agrega todos los archivos que se han modificado o creado en el directorio actual y en sus subdirectorios al _staging area_.
> - Es una opción rápida cuando quieres incluir todos los cambios realizados en el proyecto.

- Confirmar cambios (commit):

```shell
git commit -m "Mensaje descriptivo del commit"
```

- Enviar cambios al repositorio remoto:

```shell
git push
```

> [!NOTE] Nota
> El flujo es el siguiente:
> - `git add <archivo>` o `git add.`: esto agrega en el **staging area** (si no esta acá los cambios no se guarda en el commit)
> - `git commit -m "Mensaje descriptivo del commit"` todos los cambios en el _staging area_ se guardan en el historial de Git en una nueva versión (_commit_).
> - `git push` para subir los archivos

- Esto configurará Git para convertir automáticamente los finales de línea a `LF` en el repositorio y a `CRLF` en la copia de trabajo local en Windows:

```shell
git config --global core.autocrlf true
```

- Eliminar archivos del origen

```shell
git rm --cached <nombre del archivo>
```

> [!NOTE] Nota
> Esto es seguido de agregarlo a `.gitignore` y realizar un `git commit -m "eliminación del archivo"` y un `git push origin <rama donde estas trabajando>` 

- Actualizar tu repositorio local con cambios remotos:

```shell
git pull
```

```shell
git stash        # guarda los cambios no confirmados
git pull         # actualiza con los cambios remotos
git stash pop    # recupera tus cambios no confirmados
```

### Trabajo con Ramas (Branches)

- Listar ramas existentes:

```shell
git branch
```

- Listar ramas en el origen:

```shell
git branch -r
```

- Crear una nueva rama:

```shell
git branch <nombre_de_la_rama>
```

- Se utiliza para renombrar la rama actual a "main".

```shell
git branch -M main
```

- Realizar seguimiento de la rama de origen:

```shell
git branch --set-upstream-to=origin/<branch> <branch local>
```

- Cambiar a otra rama: Crear y cambiar a una nueva rama:

```shell
git checkout <nombre_de_la_rama>
```

```shell
git checkout -b <nombre_de_la_rama>
```

- Fusionar una rama con la rama actual:

```shell
git merge <nombre_de_la_rama>
```

- Eliminar una rama:

```shell
git branch -d <nombre_de_la_rama>
```

- Subir rama de trabajo:

```shell
git push -u origin <nombre_de_la_rama>
```

### Historial y Diferencias

- Ver historial de commits:Historial en una sola línea por commit:

```shell
git log
```

```shell
git log --oneline
```

- Ver diferencias entre commits o ramas:

```shell
git diff
```

- Mostrar detalles de un commit específico:

```shell
git show <id_del_commit>
```

### Deshacer Cambios

- Descartar cambios en el directorio de trabajo:

```shell
git checkout -- <archivo>
```

- Retirar archivos del área de preparación:

```shell
git reset <archivo>
```

- Deshacer el último commit pero mantener los cambios:

```shell
git reset --soft HEAD~1
```

- Deshacer el último commit y los cambios:

```shell
git reset --hard HEAD~1
```

### Trabajo con Repositorios Remotos

- Listar repositorios remotos:

```shell
git remote -v
```

- Añadir un repositorio remoto:

```shell
git remote add origin <url_del_repositorio>
```

- Cambiar la URL de un repositorio remoto:

```shell
git remote set-url origin <nueva_url>
```

- Obtener datos del remoto sin fusionar:

```shell
git fetch
```

### Etiquetado (Tags)

- Crear una etiqueta ligera:

```shell
git tag <nombre_de_la_etiqueta>
```

- Crear una etiqueta anotada:

```shell
git tag -a <nombre_de_la_etiqueta> -m "Mensaje de la etiqueta"
```

- Listar todas las etiquetas:

```shell
git tag
```

- Enviar etiquetas al repositorio remoto:

```shell
git push origin --tags
```

### Almacenamiento Temporal (Stashing)

- Guardar cambios sin confirmar:

```shell
git stash
```

- Listar elementos en el stash:

```shell
git stash list
```

- Aplicar el último stash y eliminarlo de la lista:

```shell
git stash pop
```

- Aplicar un stash específico:

```shell
git stash apply stash@{número}
```

## Los estados más comunes en git

En Git, los archivos pueden tener varios estados según el flujo de trabajo. Los estados más comunes son:

1. **Untracked (Sin seguimiento)**: Son archivos nuevos que Git no está rastreando. Estos archivos no están en el área de preparación (staging) y no se incluirán en el próximo commit hasta que los agregues.

2. **Tracked (Rastreado)**: Archivos que Git está rastreando y que se han añadido en algún commit anterior. Los archivos rastreados pueden estar en diferentes sub-estados:

   - **Unmodified (Sin modificar)**: Son archivos que están en el repositorio y que no han cambiado desde el último commit. Git no realizará ninguna acción sobre ellos a menos que se modifiquen.

   - **Modified (Modificado)**: Son archivos rastreados que han cambiado en el sistema de archivos local pero que no han sido añadidos al área de preparación (staging). Git detecta que estos archivos han sido alterados desde el último commit.

   - **Staged (En preparación)**: Son archivos modificados que se han añadido al área de preparación (staging area) con `git add`. Están listos para ser incluidos en el próximo commit.

3. **Committed (Confirmado)**: Los cambios en estos archivos se han guardado en el historial del repositorio. Una vez que haces un commit, el estado de los archivos cambia de staged a committed.

Para resumir, los estados principales en Git son: **Untracked**, **Unmodified**, **Modified**, **Staged** y **Committed**.

## Copia de Seguridad Rápida de Cambios de Git (Archivos Modificados y Nuevos)

Copia los archivos que estan en `git status -s` y los manda a una carpeta a esta dirección `$HOME\Desktop\temp_cambios` eso sería de función

```powershell
$dest = "$HOME\Desktop\temp_cambios"; New-Item -ItemType Directory -Force -Path $dest | Out-Null; git status -s | Where-Object { $_ -match "^ M|^A|^?? " } | ForEach-Object { $source = $_.Substring(3).Trim(); $fileName = Split-Path $source -Leaf; Copy-Item $source -Destination "$dest\$fileName" }; Invoke-Item $dest
```

>Esto genera una copia en desktop de los archivos que vas modificando para proporcionar los archivos utilizado a la IA y pueda realizar análisis a partir de ello.