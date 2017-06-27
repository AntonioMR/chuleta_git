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

`$ git init`

---

## Clonar repositorios (clone)
| casos de uso | comando |
|--------|--------|
|Clonar repositorio desde url| `$ git clone [url]`|
|Clonar repositorio desde url en directorio| `$ git clone [url] <dir>` |

---

## Revisando el estado del repoitorio (status)
| casos de uso | comando |
|--------|--------|
|Ver estado de ficheros | `$ git status` |
|Ver estado de ficheros en formato abreviado| `$ git status -s` |

---

## Añadiendo archivos al staging (add)

| casos de uso | comando |
|--------|--------|
|Añadir fichero | `$ git add [fichero]` |
|Añadir directorio | `$ git add [directorio/]`|
|Añadir todos los ficheros modificados | `$ git add .` |
|Añadir interactivo | `$ git add -i`|
|Añadir parte del archivo | `$ git add -p [archivo]`|

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

## Comprobando cambios (diff)

| casos de uso | comando |
|--------|--------|
|Ver todas las diferencias | `$ git diff` |
|Ver diferencias en fichero | `$ git diff [fichero]` |
|Ver diferencias en staging | `$ git diff --cached` |

---

## aparcando cambio (stash)
|Listando todos los cambios aparcado| `$ git stash list`|
| casos de uso | comando |
|--------|--------|
|Aparcando todos los cambios| `$ git stash <save>`|
|Aplicando los ultimos cambios aparcados| `$ git stash apply`|
|Borrando los cambios aparcados| `$ git stash drop stash@{0}`|
|Aplicar ultimos cambios aparcados y borrarlos de la lista| `$ git stash pop`|
|Aplicar ultimos cambios aparcados y borrarlos de la lista| `$ git stash pop`|
|Aparcar solo los cambio no añadidos al staging| `$ git stash --keep-index`|
|Decidir que cambios del fichero añadir al aparcamiento| `$ git stash --patch`|
|Mover los cambios a una nueva rama| `$ git stash branch [rama]`|

---

## Descartando cambios (clean)
| casos de uso | comando |
|--------|--------|
|Eliminar archivos sin seguimiento que no esten ignorados| `$ git clean`|
|Eliminar archivos sin seguimiento aunque esten ignorados| `$ git clean -x`|
|Eliminar archivos y directorios sin seguimiento| `$ git clean -d -f`|
|Ver que archivos y directorios se borrarán| `$ git clean -d -n`|
|Eliminar archivos de forma interactiva| `$ git clean -i`|
