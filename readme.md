# Chuleta de comandos Git

## Obteniendo ayuda (help)
`$ git help <comando>`

---

## Configurando Git: (config)
* Configuracion global: se almacena en `/etc/gitconfig` se obtiene con `--system`
* Configuracion de usuario: se almacena en `~/.gitconfig` o `~/.config/git/config` se obtiene con `--global`
* Configuracion del repositorio `.git/config`

| casos de uso | comando |
|--------|--------|
|configurar identidad nombre | `$ git config --global user.name "Nombre"` |
|configurar identidad email | `$ git config --global user.email nombre@example.com` |
|configurar editor | `$ git config --global core.editor vi` |
|comprobar configuracion | `$ git config --list` |

---

## Iniciar repositorio (init)
| casos de uso | comando |
|--------|--------|
|Iniciar un nuevo repositorio| `$ git init [nombre-proyecto]`|

---

## Clonar repositorios (clone)
| casos de uso | comando |
|--------|--------|
|Clonar repositorio desde url| `$ git clone <url>`|
|Clonar repositorio desde url en directorio| `$ git clone <url> [dir]` |

---

## Revisando el estado del repositorio (status)
| casos de uso | comando |
|--------|--------|
|Ver estado de ficheros | `$ git status` |
|Ver estado de ficheros en formato abreviado| `$ git status -s` |

---

## Añadiendo archivos al area de confirmación (add)

| casos de uso | comando |
|--------|--------|
|Añadir fichero | `$ git add <fichero>` |
|Añadir directorio | `$ git add <directorio/>`|
|Añadir todos los ficheros nuevos o modificados | `$ git add .` `$ git add -a` |
|Añadir los ficheros nuevos, modificados o eliminados | `$ git add -A` |
|Añadir los ficheros que ya estan en seguimiento | `$ git add -u` |
|Muestra lo que se añadiría | `$ git add -n` |
|Añadir interactivo | `$ git add -i`|
|Añadir parte del archivo | `$ git add -p <archivo>`|

---

## Eliminando archivos (rm)

| casos de uso | comando |
|--------|--------|
|Eliminar un fichero del disco eliminandolo del seguimiento | `$ git rm <fichero>` |
|Eliminar un fichero del disco eliminandolo del seguimiento si está en el area de confirmación | `$ git rm -f <archivo>`|
|Eliminar del seguimiento sin eliminar del disco | `$ git rm --cached <archivo>`|

---

## Renombrando archivos (mv)

| casos de uso | comando |
|--------|--------|
|Cambiar el nombre de un fichero en seguimiento | `$ git mv <nombre> <nuevoNombre>` |

---

## Confirmando cambios (commit)

| casos de uso | comando |
|--------|--------|
|Realizar commit añadiendo el texto descriptivo mediante el editor por defecto | `$ git commit` |
|Realizar commit añadiendo el texto descriptivo directamente | `$ git commit -m "descripcion del commit"` |
|Realizar commit añadiendo al area de confirmación todos los ficheros modificados| `$ git commit -a -m "descripcion del commit"` |
|Cambiar el mensaje o añadir cambios al ultimo commit| `$ git commit --amend` |

---

## Deshaciendo cambios (reset, checkout)

| casos de uso | comando |
|--------|--------|
|Sacar cambios del area de confirmacion | `git reset [HEAD] [<archivo>]` |
|Deshacer un commits apuntando HEAD a un commit concreto | `git reset HEAD <commit_checksum>` |
|Deshacer el ultimo commits apuntando HEAD al commit anterior (deshace commit)| `git reset --soft HEAD~` |
|Deshacer el ultimo commits apuntando HEAD al commit anterior (deshace commit y add) | `git reset [--mixed] HEAD~` |
|Deshacer el ultimo commits apuntando HEAD al commit anterior (deshace commit, add y directorio de trabajo. Los cambios se perderan) | `git reset --hard HEAD~` |
|Descartar cambios no confirmados realizados en un archivo (se perderan) | `git checkout -- [archivo]` |

---

## Ignorando archivos (.gitignore)

| casos de uso | comando |
|--------|--------|
|ignorar ficheros con extension bak | `*.bak` |
|añadir excepcion a regla previa | `!lib.bak` |
|ignorar directorios | `directorio/` |
|ignorar ficheros en un directorio | `ruta/*.txt` |
|ignorar ficheros en un directorio recursivamente| `ruta/**/*.txt` |

---

## Historial de cambios (log)

| casos de uso | comando |
|--------|--------|
|Mostrar los ultimos commits | `$ git log` |
|Mostrar los 'n' ultimos commits | `$ git log -n` |
|Mostrar los ultimos commits mostrando diferencias introducidas| `$ git log -p` |
|Mostrar los ultimos commits mostrando estadisticas | `$ git log --stat` |
|Mostrar los ultimos commits aplicando formato de una linea | `$ git log --pretty=oneline` |
|Mostrar los ultimos commits aplicando formato expecífico | `$ git log --pretty=format:"%s"` |
|Mostrar los ultimos commits mostrando un grafico de ramificacion | `$ git log --graph` |
|Mostrar los ultimos commits mostrando donde apuntan las ramas creadas | `$ git log --decorate` |
|Ver commits realizados en la rama "rama" no fusionados en la rama master | `$ git log master..<rama>` `$ git log ^master <rama>` |
|Ver commits realizados en varias ramas no fusionados en la rama master | `$ git log <rama1> <rama1> ^master` |
|Ver los cambios que vamos a subir al repositorio remoto si hacemos push| `$ git log origin/master..HEAD` |
|Ver los cambios realizados entre dos ramas indicando a que rama corresponden los cambios| `$ git log [--left-right] <rama1>...<rama2>` |
|Ver los cambios realizados entre dos ramas que modifican  archivos en conflicto tras un merge| `$ git log [--left-right] --merge` |

---

## Comprobando cambios (diff)

| casos de uso | comando |
|--------|--------|
|Ver todas las diferencias | `$ git diff` |
|Ver diferencias en fichero | `$ git diff <fichero>` |
|Ver diferencias en el area de confirmación | `$ git diff --cached` |

---

## aparcando cambio (stash)
| casos de uso | comando |
|--------|--------|
|Aparcando todos los cambios| `$ git stash [save]`|
| Listando todos los cambios aparcados | `$ git stash list`|
|Aplicando los ultimos cambios aparcados| `$ git stash apply`|
|Borrando los cambios aparcados| `$ git stash drop stash@{0}`|
|Aplicar ultimos cambios aparcados y borrarlos de la lista| `$ git stash pop`|
|Aparcar solo los cambio no añadidos al area de confirmación| `$ git stash --keep-index`|
|Decidir que cambios del fichero añadir al aparcamiento| `$ git stash --patch`|
|Mover los cambios a una nueva rama| `$ git stash branch <rama>`|

---

## Descartando cambios (clean)
| casos de uso | comando |
|--------|--------|
|Eliminar archivos sin seguimiento que no esten ignorados| `$ git clean`|
|Eliminar archivos sin seguimiento aunque esten ignorados| `$ git clean -x`|
|Eliminar archivos y directorios sin seguimiento| `$ git clean -d -f`|
|Ver que archivos y directorios se borrarán| `$ git clean -d -n`|
|Eliminar archivos de forma interactiva| `$ git clean -i`|


---

## Repositorios remotos (remote)
| casos de uso | comando |
|--------|--------|
|Ver los repositorios remotos configurados (solo nombre)| `$ git remote`|
|Ver los repositorios remotos configurados (nombre y url)| `$ git remote -v`|
|Añadir repositorio remoto| `$ git remote add <nombre-remoto> <url-remoto>`|
|Inspeccionar repositorio remoto| `$ git remote show <nombre-remoto>`|
|Renombrar repositorio remoto| `$ git remote rename [nombre-remoto] [nuevo_nombre-remoto]`|
|Eliminar repositorio remoto| `$ git remote rm <nombre-remoto>`|

---

## Trayendo cambios de repositorios remotos (fetch)
| casos de uso | comando |
|--------|--------|
|Traer informacion de cambios del remoto "origin"| `$ git fetch`|
|Traer informacion de cambios del un repositorio remoto concreto| `$ git fetch <nombre-remoto>`|

---

## Llevando cambios de repositorios remotos (push)
| casos de uso | comando |
|--------|--------|
|Llevar cambios registrados al remoto "origin"| `$ git push`|
|Llevar cambios registrados a remoto concreto | `$ git push <nombre-remoto>`|
|Llevar cambios de una rama al remoto "origin" | `$ git push origin <rama>`|
|Llevar una etiqueta al remoto "origin" | `$ git push origin <tag>`|
|Llevar todas las etiquetas al remoto "origin" | `$ git push origin --tags`|

---

## Etiquetando commits (tag)
| casos de uso | comando |
|--------|--------|
|Listar etiquetas disponibles| `$ git tag`|
|Listar etiquetas que cumplen con un criterio| `$ git tag -l 'V1.*'`|
|Crear etiqueta anotada| `$ git tag -a <tag_name> [-m 'comentario de etiqueta']`|
|Crear etiqueta anotada en un commit anterior| `$ git tag -a <tag_name> <commit_checksum>`|
|Crear etiqueta ligera| `$ git tag <tag_name>`|

---

## Utilizando ramas (branch)
| casos de uso | comando |
|--------|--------|
|Listar ramas disponibles| `$ git branch`|
|Listar ramas viendo ultimos cambios confirmados en cada rama| `$ git branch -v`|
|Listar ramas fusionadas en la rama activa| `$ git branch --merged`|
|Listar ramas con trabajos sin fusionar en la rama activa| `$ git branch --no-merged`|
|Crear ramas | `$ git branch <rama>`|
|Borrar ramas sin cambios pendientes de fusionar| `$ git branch -d <rama>`|
|Borrar ramas con cambios pendientes de fusionar| `$ git branch -D <rama>`|

---

## Moviendose entre ramas (checkout)
| casos de uso | comando |
|--------|--------|
|Cambiar de rama activa| `$ git checkout <rama>`|
|Cambiar de rama activa creando la nueva rama| `$ git checkout -b <rama>`|

---

## Fusionando ramas entre ramas (merge)
| casos de uso | comando |
|--------|--------|
|Fusionar rama en la rama activa| `$ git merge <rama>`|
|Fusionar rama en la rama activa sin dejar commit de la fusión| `$ git merge <rama> --no-commit`|
|Fusionar evitando conflictos por espacios en blanco| `$ git merge -Xignore-all-space <rama>`|
|Abortar una fusion que reporta conflictos| `$ git merge --abort`|
|Fusionar rama y en caso de conflicto resolver con los cambios en la rama actual| `$  git merge -Xours <rama>`|
|Fusionar rama y en caso de conflicto resolver con los cambios en la rama a fusionar| `$  git merge -Xtheirs <rama>`|

---

## Reorganizando ramas (rebase)
| casos de uso | comando |
|--------|--------|
|Reorganizar rama activa sobre otra| `$ git rebase <rama>`|
