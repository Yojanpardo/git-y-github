# Curso profesional de git y github de platzi

aquí está toda la documentación de lo que estoy apremdiendo, diferentes notas y mis proyectos.
es gracioso iniciar el repositorio de git y github despues de casi 40 repositorios :v pero bue.

Git es un sistema de control de versiones que permite registrar los cambios realizados sobre un archivo o conjunto de archivos en el transcurso del tiempo.

## Tipos de repositorios
* Local
	sistema de control de versiones que vive completamente en mi computador, no sale a internet.
* Centralizado
	extiende los poderes del sistema local porque utiliza un servidor el cual almacena mis repositorios, ya no depende unicamente de mi pc sino que está soportado en un servidor web. si se quema el servidor nos mamamos.
* Distribuido
	está repartido en cada uno de los participantes en el repositorio, es decir: a un repositorio colaboran varios desarrolladores, para esto cada desarrollador descarga el repositorio y lo tiene localmente, puede hacer son él lo que quiera sin afectar a los demas.

## Un poco de historia
por el 2002 el proyecto de linux debia estar bajo en un sistema de control de versiones, entonces linux se asocia con bitkeeper para que almacenara el nucleo de linux, en el 2005 bitkeeper le quita la licencia gratuita a linux, linux no se mueve con dinero como para andar pagando licencias, así que linus tolvards dice "voy a hacer mi propio sistema de control de versiones con juegos de azar y mujerzuelas"  de esta manera nació git.

git cuenta con varias caracteristicas entre las cuales encontramos que git es mas veloz, tiene un diseño sencillo tiene apoyo para el desarrollo no lineal, es decir que se pueden hacer muchas cosas al mismo tiempo, está completamente distribuido y puede manejar grandes proyectos.

## Los estados de Git
En Git nos encontramos con 3 posibles estados de nuestros proyectos. entre los cuales encontramos:
* Working directory: es nuestro repositorio local en el cual trabajamos, los cambios que realicemos aquí no van a ser tenidos en cuenta sino hasta que los pasemos a nuestro stagin area.
* Stagin area: aquí es donde estan nuetros archivos que hemos guardado del trabajo en Working area y se preparan los archivos para llevarlos al git repository con un commit.
* Git repository: aqui están almacenados todos los datos del repositorio, con camios y toda la cosa.

## Git y Github
- Git es nuestro sistema de control de versiones, puede trabajar perfectamente sin github pero estaría unicamente en nuestro pc.
- Github es una plataforma en la cual se almacenan nuestros repositorios y otros desarrolladores pueden aportar a nuestros proyectos, github es como una red social.

## Instalando y configuando Git
En esta ocasión estoy utilizando Ubuntu Gnome 17.10
para instalarlo ejecutamos el comando

	$ sudo apt install git -y

Ahora que tenemos git instalado debemos indicarle quien es la persona que va a manejar git, es decir, debemos ingresar nuestro email y nombre con los siguientes comandos.

	$ git config --global user.name "Nombre del propietario"
	$ git config --global user.email "email del usuario"

así pues ya tenemos nuestro git instalado y listo para usar.

adicionalmente a ésto podemos decirle a git que active los colores para que nuestra terminal sea menos aburrida.

	$ git config --global color.ui true

puedes encontrar ésta y muchas mas configuraciones de git [haciendo click aquí](https://git-scm.com/).

## Comandos de la terminal
Para trabajar con git en la terminal debemos saber unos cuantos comandos, aquí enseñaré los mas basicos:

	$ cd [ruta de una carpeta] -nos permite movernos entre los directorios del sistema
	$ ls -nos lista el contenido del directorio en el que nos encontremos
	$ls -a -muestra los archivos ocultos
	$ clear -limpia la terminal
	$ mkdir [nombre del directorio nuevo] -crea un nuevo directorio
	$ touch [nombre del archivo] -crea un archivo con el nombre que le ingresamos, es importante añadir la extensión del archivo
	$ rm [nombre del archivo] -borra el archivo al que nombraste
	$ rm -rf [nombre del directorio] elimina el directorio nombrado
a veces es necesario editar archivos dentro de la terminal asi que para ello podemos utilizar un editor de texto dentro de la terminal como poe ejemplo vim.

para instalar vim en Ubuntu

 	$ sudo apt install vim
para ejecutar vim y escribir en un archivo de texto

	$ vim [nombre del archivo con la extensión]

dentro de vim existen unos comandos para poder guardar y salir del editor:
oprimimos la tecla esc y aqui podemos escribir ciertos comandos

	:wq -guarda el archivo y sale del editor
	:q! -para salir sin guardar nada alvt

## Creando un nuevo proyecto (git init)
Para iniciar un nuevo repositorio ejecutamos el siguiente comando

	$git init -Inicia un nuevo proyecto en la carpeta en la que se encuntran parados
	$git init [nombre del proyecto] -crea una carpeta con el nombre ingresado y en ella inicia el nuevo repositorio

Para eliminar un repositorio lo hacemos con el siguiente comando

	$ rm -rf .git -esto elimina la carpeta de .git que tiene almacenados los datos del repositorio.

## Añadiendo archivos al stagin area
antes que nada podemos revisar si tenemos archivos sin añadir al staging area

	$ git status -nos muestra el estado de los archivos de nuestro proyecto.
para ello utilizamos el siguiente comando

	$ git add [archivo] -para añadir un archivo en especifico
	$ git add -A -para añadir todos los archivos que estén sin añadir
	$ git add -n [archivo] -con este comando se selecciona un archi para que no sea tomado en cuenta para pasarlo al staging area  

podemos hacer el siguiente comando para quitar devolvernos

	$ git rm --cached [Archivo]
	$ git rm -f [archivo] -elimina un archi de forma permanente

## añadiendo archivos al git directory
una vez que tenemos todos nuestros archivos en staging area procedemos a acer un commit para que de esta manera nuestros archivos sean confirmados dentro de nuestro repositorio.

		$ git commit -m ["descripción corta de lo que se hizo en este comit"]
		$ git commit -m ["mensaje"] --amend -concatena el commit nuevo con el commit anterior
y ahora solo debemos escribir nuestro "nuevo comando" para ver nuestro registro bien chidori

	$ git slog

## Etiquetando nuestro proyecto
existen dos tipos de etiquetas:
- light with (ligeras) es la version de como vamos a etiquetar (1.0, 2.0, etc)
- anotated (anotadas) requiere el nombre de referencia de la etiqueta  y una anotacion

etiqueta ligera.

	$ git tag 1.1
etiqueta anotada

	$ git tag -a 2.0 -m "version estable del proyecto"

para ver la etiqueta

	$ git tag -l

para etiquetar un commit anterior al que nos encontramos parados debemos utilizar el Hash del commit que queremos etiquetar.

	$git tag -a 0.3 [hash]

para renombrar y borrar

	$ git tag -f -a [nueva etiqueta] -m ['nueva anotacion'] [SHA-1]
	$ git tag -d [tag]
## Revisando nuestro proyecto
para ello utilizamos el comando

	$ git log
a medida que avanzamos en nuestro proyecto van a ir apareciendo más commits así que podemos ver la historia de nuestro proyecto mas ordenada o mas resumida.

 	$ git log --oneline

podemos ver solo los commits que queramos, por ejemplo si solo queremos ver los dos ultimos utilizamos

	$ git log -2
Tambien podemos combinar varios flags en nuestro log. por ejemplo:

	$ git log --oneline --graph

puedes encontrar mas en la [documentacion de git](https://www.git-scm.com/docs/git-log)

el siguiente es un comando super chingon que nos permite ver todos nuestros comits de una forma super cool pero para ello debemos configurar un alias primero asi que escribimos esto en nuestra terminal

	$ git config --global alias.slog 'log --graph --abbrev-commit --decorate --date=relative --format=format:"%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white) - %an%C(reset)%C(bold yellow)%d%C(reset)" --all'
## Revisando cambios entre versiones
Es necesario revisar los cambios realizados de una version a otra para no cometer nuevamente mismos errores y saber que es lo que le hace falta a nuestro proyecto. para ello utilizamos

	$ git diff [SHA-1]
nos muestra los cambios realizados en ese commit

si queremos comparar diferentes commits entonces lo hacemos de la siguiente manera

	$ git dif [SHA-1] [SHA-1]

## Regresando en el tiempo
de vez en cuando la cagamos y necesitamos deshacer cambios o hacer como un ctrl-z asi que para ello utilizamos reset con sus diferentes flags

	$ git reset --soft [SHA-1]

ponemos el SHA-1 del comit desde el que queremos eliminar los commits, nos deja lo que tenemos en el staging area listos para hacer commit, como tal no elimina archivos.

	$ git reset --mixed [SHA-1]
Elimina tambien los cambios en el staging area, a partir de aqui debemos hacer un git add y git commit

	$ git reset --hard [SHA-1]
elimina absolutamente todo, incluso los archivos en el working directoy.

si la cagamos y no queriamos borrar algo debemos regresarnos al estado en el que estabamos completamente seguros. Git reset --hard no afectará los archivos que no hayamos añadido.

## Configurando otro editor

	$ git config --global core.editor "[nombre del editor] --wait"

# Hablemos de ramas y mundos paralelos
Git tiene grandes herramientas como por ejemplo trabajar en paralelo con diferentes desarrolladores

## creando nuevas ramas

	$ git branch [nombre-de-la-rama]
	$ git branch -l --para listar las ramas existentes
	$ git branch -D [nombre] --elimina la rama nombrada
	$git branch -m [nombre-viejo] [nuevo-nombre] -- para renombrar ramas

## Git checkout

	$ git checkout [nombre] -nos mueve a una rama
	$ git checkout [SHA-1] --nos movemos a un commit anterior
	$ git checkout -b [nombre] --creamos una rama nueva
	git checkout -- <file> --nos permite eliminar los cambios realizados sobre un archivo que no esté en el staging area.

## trabajando en paralelo
ti tenemos archivos untraked y cambiamos de rama, éstos archivos se van a mover de donde los dejamos hacia la rama en donde estamos parados.

## git merge
cuando vamos a mezclar los cambios realizados en nuestras otras ramas debemos hacer lo siguiente:

1. nos paramos en la rama en la cual queremos mezclar los cambios, en este caso lo haremos en master:

	$ git checkout master
2. ahora le decimos que es lo que queremos mezclar. para ello utilizamos el siguiente comando.

	$ git merge [nombre de la rama que queremos mezclar]
si todo está en orden nos hará un fast-forward si no entonces debemos hacer un merge recursivo lo que nos hace selecconar los cambios manualmente

# Reescribiendo la historia de nuestro proyecto

vamos a aprender a utilizar git rebase que es practicamente lo mismo que un merge pero no crea bifurcaciones, solo usarlo localmente, es mejor utilizar merge para que se vea mas claro que es lo que se está haciendo.

	$ git rebase
	$ git rebase -i --abre una ventana interactiva para hacer nuestro rebase.

## Guardando cambios temporalmente
En el momento en el que tenemos cambios que no estamos seguros de aplicar o si tenemos que dejar a medias lo que estamos haciendo podemos guardar nuestros cambios sin confirmarlos.

	$ git stash  --nos guarda el estado actual sin confirmarlo
	$ git stash list --nos muestra un listado de nuestros stash
	$ git stash drop stash@[{numero}] --elimina el stash seleccionado
	$ git stash apply stash@[{numero}]--aplica los cambios almacenados en la lista de los stash
git stash solo almacena los cambios realizados que estén almacenados en el staging.

## git cherry-pick
nos permite seleccionar commits para moverlos a otras ramas

	$ git cherry-pick [SHA-1]
