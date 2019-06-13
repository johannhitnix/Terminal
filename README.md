# Listado de comandos en Terminal

### ls
 > sirve para listar los archivos, tiene banderas **-l, -lh, -lha* *

·`ls` => lista los directorios de forma vertical

·`ls -h` => list, human readable

·`ls -l` => list, long

·`ls -a` => list, all

·`ls -lha` => list, long, human readable, all

### cd
> change directory

·`cd ~` y `cd` => go to home, el simbolo **~** es virgulilla

### touch
> crea archivos

·`touch ejemplo.txt` => crea el archivo ejemplo.txt

### mkdir
>*Make directory* crea directorios

·`mkdir folder` => crea el directorio folder

### mv

> Move

·`mv nombre-viejo nombre-nuevo` => cambia de nombre un archivo, lo mueve

·`mv <archivo> [ruta-directorio/]` => me mueve el archivo a la **ruta-directorio/**

###rm

>Elimina archivos, links y carpetas

·`rm <archivo>` => elimina el archivo especificado

·`rm -rf <folder>` => borra recursivamente un folder y su contenido

###man
> Manual

·`man <comando>` => muestra el manual del comando solicitado, se sale con **q**

###pushd & popd

>Es un stack de directorios y sirve para saltar de directorio en directorio sin usar **cd**

·`pushd [ruta-directorio/]` => me lleva a la **ruta-directorio/** y la inserta en la pila

·`popd` => saca la ruta de la pila y me devuelve de un salto a donde estaba antes

