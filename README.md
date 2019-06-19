# 😎 Listado de comandos en Terminal 😜

### ls
> sirve para listar los archivos, tiene banderas **-l, -lh, -lha* *

·**`ls`** => lista los directorios de forma vertical

·**`ls -h`** => list, human readable

·**`ls -l`** => list, long

·**`ls -a`** => list, all

·**`ls -lha`** => list, long, human readable, all

> **WildCard `*`**

·**`ls -l sal*`** => lista todas las opciones que tengan la cadena antes del **`*`**

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

·**`tail -f std_out`** => imprime la ultima linea de un archivo en este caso **std_out**, no importa si es un archivo que esta siendo actualizado constantemente por un programa termino la ejecución con **ctrl+c**

### which
>Revela el origen de un comando

·**`which [cmd]`** => muestra en que directorio esta el comando

### alias

>alias para un comando

·**`alias <mi-alias>='[cmd]'`** => puedo encapsular comandos con cualquier alias que le ponga y ese comando puede ser llamado despues con el alias que le puse

### variables
>Las variables en consola comienzan con $, pej $PATH

·**`echo $PATH`** => imprime la ruta

### Streams
>existen 3 tipos de streams:
-> standard input (StdIn)
-> standard output (StdOut)
-> standard error (StdError): manda los errores a un archivo de errores

>si el archivo no existe lo crea y empieza a escribir desde cero

·**`php streams.php > std_out`** => ejecuta el archvio **streams.php** y manda los resultados al archivo **std_out** termino la ejecución con **ctrl+c**

>Usa dos variables **`1`** StreamOutput y **`2`** StreamError

·**`php streams.php 1> salida 2> error`** => ejecuta el archivo y manda en dos archivos distintos los output y los errores

> **`>>`** concatenar

·**`php streams.php >> std_out`** => concatena los resultados en un archivo existente

> **2>&1** 

·**`php stream.php > todo.log 2>&1`** => Aqui se mando todo lo del stream 2 a donde se mande lo del stream 1 al archivo **todo.log**

>Ejemplo mysql

·**`mysql -u root -p < all_schema.sql`** => al ejecutar pide el password y ejecuta el script en mysql

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

### procesos

>correr en background

·**`php streams2.php 3 > salida.log 2>&1 &`** => con **&** al final se ejecuta el proceso en background y muestra su respectivo **pid**

>secuencia de procesos

·**`php streams2.php 4; echo "ya termine!"; php streams2.php 7`** => despues de terminar con el proceso 1 se sigue con el proceso 2 y asi sucesivamente concatenandolos con **`;`**


## Power Tools 

### grep

>flags:
**-r** recursivamente,
**.** todos los archivos y directorios abajo, 
**-e** expresión

·**`grep -r . -e [palabra-a-buscar]`** => da como resultado la linea del archivo donde esta la palabra

>**directorio/**

·**`grep -r directorio/ -e [palabra-a-buscar]`** => aqui se especifico el directorio donde quiero buscar

>**file**

·**`grep <file> -e [palabra a buscar]`** => busca en un solo archivo

>flag **-c** (count)

·**`grep <file> -c -e [palabra-a-buscar]`** => muestra el numero de veces que la palabra aparece en el archivo

·**`grep <file> -e [palabra-a-buscar] | wc -l>`** => se obtiene un resultado similar con este método propuesto en el curso

> flag **-n**

·**`grep -n -r . -e [palabra-a-buscar]`** => me adiciona el numero de linea donde aparece la palabra


### date

> truco para saber cuanto tarda un proceso

·**`date; grep -r . -e ALARMA; date`** => hago un sandwich de dos date con un proceso y la diferencia de los dates me da una idea de cuanto se tardo


### find

> busca cadenas en los archivos por su metadata: nombres, tipo de archivo, etc

·**`find . -name '*.php' -type f`** => busca los archivos cuyo nombre termine en *.php* y que el tipo de archivo sea file

> **| wc -l**

·**`find . -name '*.php' -type f | wc -l`** => muestra el conteo de archivos con esas caracteristicas

> **more**

·**`find . -name '*.php' | more`** => para paginar 

> **type d** (directorio)

·**`find . -type d`** => va a buscar todos los tipo directorio 

>busqueda en raiz **~/**

·**`date; find ~/ -name '*.php' -type f > resultados_php; date`** => busca todos los archivos php en mi computadora, todo lo guarda en el archivo **resultados** y muestra cuanto tarda con los date

> comando complementario **wc**

·**`wc -l resultados_php`** => muestra el numero de lineas del archivo en este caso el numero de archivos php encontrados

>ver todos los archivos

·**`date; find ~/ -type f | wc -l; date`** => cuenta el total de archivos de mi computadora

### curl

> emula los requests de un browser

·**`curl [url] > aeropuertos.csv`** => trae todos los datos de la url dentro de mi archivo **aeropuertos.csv**

### zip

>comprime en un formato de valido par windows linux y mac

·**`zip varios_csv.zip *.csv`** => comrime los archivos **csv** en un archivo **zip**

### unzip

>descomprime los zip

·**`unzip varios_csv.zip`** => descomprime el zip pero no lo destruye

>**-vl**

·**`unzip -vl varios_csv.zip`** => no descomprime como tal, los descomprime de manera virtual y los lista con todos sus detalles 

### tar

>**cfz** create file zip

·**`tar cfz varios_csv.tar.gz *.csv`** => crea un archivo **.tar.gz** y le añade los archivos en este caso los .csv y pesa un poquito menos que un zip

>**xfz** extract file zip

·**`tar xfz varios_csv.tar.gz`** => extrae lo que hay en un archivo **.tar.gz**

### awk

> Hace un exploit de un archivo separado por algun tipo de caracteres
**-F** es el formato de separar columnas
usa sintaxsis de **C** recordando que **%s** significa string
**$2** es el campo de la segunda columna en el archivo

·**`cat archivo.csv | awk -F"::" '{printf("%s - %s\n", $3 $2 )}' | more`** => muestra en pantalla la tercera y despues la segunda columna del archivo y concatena al final con **more**



