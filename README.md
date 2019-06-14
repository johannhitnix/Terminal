# Listado de comandos en Terminal

### ls
 > sirve para listar los archivos, tiene banderas **-l, -lh, -lha* *

·**`ls`** => lista los directorios de forma vertical

·**`ls -h`** => list, human readable

·**`ls -l`** => list, long

·**`ls -a`** => list, all

·**`ls -lha`** => list, long, human readable, all

### cd
> change directory

·**`cd ~`** y **`cd`** => go to home, el simbolo **~** es virgulilla

### touch
> crea archivos

·**`touch ejemplo.txt`** => crea el archivo ejemplo.txt

### mkdir
>*Make directory* crea directorios

·**`mkdir folder`** => crea el directorio folder

### mv

> Move

·**`mv nombre-viejo nombre-nuevo`** => cambia de nombre un archivo, lo mueve

·**`mv <archivo> [ruta-directorio/]`** => me mueve el archivo a la **ruta-directorio/**

### rm

>Elimina archivos, links y carpetas

·**`rm <archivo>`** => elimina el archivo especificado

·**`rm -rf <folder>`** => borra recursivamente un folder y su contenido

### man
> Manual

·**`man <comando>`** => muestra el manual del comando solicitado, se sale con **q**

### pushd & popd

>Es un stack de directorios y sirve para saltar de directorio en directorio sin usar **cd**

·**`pushd [ruta-directorio/]`** => me lleva a la **ruta-directorio/** y la inserta en la pila

·**`popd`** => saca la ruta de la pila y me devuelve de un salto a donde estaba antes

### more & less
>Revelan el contenido de un archivo en terminal

·**`more <file>`** => Sirve para ver las primeras lineas de un archivo

·**`less <file>`** => Muestra las lineas de un achivo y a diferencia de more hay que presionar **q** para salir

### cat
>(concat) 2 propositos: revela el contenido o concatena contenido

·**`cat <file>`** => Muestra todo el contenido de un archivo

·**`cat > <file>`** => Abre un editor para concatenar texto al archivo, se cierra con **ctrl+c**

### tail
>(cola) Revela ultimas lineas de un archivo

·**`tail <file>`** => muestra las ultimas 10 lineas de un archivo 

·**`tail -15 <file>`** => muestra las ultimas 15 lineas de un archivo

### which
>Revela el origen de un comando

·**`which [cmd]`** => muestra en que directorio esta el comando

### alias

>alias para un comando

·**`alias <mi-alias>='[cmd]'`** => puedo encapsular comandos con cualquier alias que le ponga y ese comando puede ser llamado despues con el alias que le puse

### variables
>Las variables en consola comienzan con $, pej $PATH

·**`echo $PATH`** => imprime la ruta

### Stream
>existen 3 tipos de streams:
-> standard input (StdIn)
-> standard output (StdOut)
-> standard error (StdError): manda los errores a un archivo de errores

·**`php streams.php > std_out`** => ejecuta el archvio **streams.php** y manda los resultados al archivo **std_out**

### top
>Muestra los procesos que se estan ejecutando

·**`top`** => si presiono despues **`o`** me pide un criterio para ordenar los procesos, un criterio puede ser **cpu**, o **pid**. Me salgo de top presionando **`q`**

### kill
>Mata un proceso sin solicitar respuesta, es lo mas cercano al procesador

.**`kill -9 <pid>`** => mata el proceso especificando su **pid**, pej *"kill -9 42336"* 

### ps

>Muestra el listado de procesos sin interaccion hay dos versiones de este cmd: la de Linux y la de Mac

·**`ps -wA`** => listado sin interaccion vesion de Mac

·**`ps -wS`** => listado sin interaccion version de Linux

> **wc** (word-count), **|**(pipe)

·**`ps -wA | wc -l`** => muestra el numero de procesos en ejecución.

>**grep**

·**`ps -wA | grep [key-word]`** => busca que procesos tiene esa palabra clave, pej *ps -wA | grep ttys00*

### uptime

>me dice cuanto lleva encendido el mac

·**`uptime`** => dice la hora, cuanto tiempo lleva prendido, cuantos usuarios y la carga promedio
