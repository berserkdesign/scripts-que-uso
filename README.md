# scripts que uso
Script para GNU/Linux en Bash que me han sido útiles

1. Cómo generar tus propios scripts

Generar un nuevo comando basado en combinaciones de otros comandos y acaso con un poquito de programación básica en bash es divertido.

Primero tenemos que saber cuál es el contenido de la variable $PATH, con un comando como éste:

echo $PATH

Quizás encontréis algo parecido a esto:

/home/pablo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games

Supongo que no todo el mundo tendrá el directorio /home/su_nombre_de_usuario/bin en la variable $PATH y también es posible que alguien le quiera dar otro nombre a la carpeta que contiene los scripts de usuario. Por ejemplo, podría querer tener un directorio oculto llamado ".mis-scripts" (ojo al punto delante para que automáticamente se convierta en oculto).

En este caso, lo que queremos es añadir "/home/nombre_usuario/.mis-scritps" a la variable PATH. Esto lo podemos hacer de la siguiente forma:

gedit ~/.bashrc

La virguililla "~" es lo mismo que "/home/nombre_de_usuario_que_está_logeado". (Para saber qué usuario está logeado o bien si nos da un ataque de amnesia, podemos usar el comando whoami). Si no queréis copiar y pegar, en el teclado español podemos imprimir en pantalla la virguililla con la combinación [Alt Gr - Ñ] o con [Alt Gr - 4].

El caso es que al final del archivo .bashrc añadimos la siguiente línea:

PATH=/home/nombre_de_usuario/.mis-scripts:$PATH

Por supuesto, el directorio .mis-scripts deberá existir. Lo podemos crear con botón derecho dentro de nuestra carpeta personal. O bien con el comando:

mkdir ~/.mis-scripts

o el nombre que se os ocurra, u oculto o no oculto.

Adelántadome un poco para no perder más tiempo reiniciando cuando lleguemos al paso 4, si usamos gnome y nautilus (que traen por defecto las distros mayoritarias) vamos a instalar ahora el paquete "nautilus-open-terminal". Ya que tenemos la terminal abierta, sólo hay que copiar el comando:

sudo apt-get install nautilus-open-terminal

En el siguiente logueo del usuario (o arranque del ordenador) comprobamos otra vez con "echo $PATH" si el directorio elegido forma parte de PATH.

Bueno, pues ahora todos los scripts de bash ejecutables que estén en este directorio se pueden ejecutar simplemente invocando el nombre del archivo.


chmod +x /usr/local/bin/*
