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
