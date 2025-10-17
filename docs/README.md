
#  Debian VENENUX Desktop

Este directorio construye un debian una imagen ISO/USB mix, sin necesidad de instalar, 
esta instalacion trae `mate` como escritorio.

This directory builds a debian image USB/ISO mixed, like a hard disk made, 
this installation comes with `mate` desktop.

## Requerimientos

* Debian estable
* 2018+ year pc
* 22Gb disco libre
* 60Kbps internet minimo
* 2GHz CPU minimo
* 2Gb swap minimo
* 2G RAM minimo

## Proceso

El proceso aqui esta descrito para una persona nivel medio incluso ciega.

Descarge las fuentes del proyecto o mejor dicho el directorio que contiene este archivo que esta leyendo.

Encontrara en esas fuentes un directorio llamado `config` y otro llamado `docs` donde esta este archivo que esta leyendo actualmente.

En la raiz de este repositorio (encima de este directorio docs) es donde siempre debera trabajar, ejecute el siguiente comando:

`apt install -y live-build xorriso lsb-release file rsync wget xz-utils git zstd`

Esto instalara varios programas y una vez terminado dependiendo de su conexion de internet ejecute en el mismo raiz de las fuentes el siguiente comando:

`lb clean --purge`

Este comando con el argumento purge solo debe realizarlo esta primera vez, las siguientes seran sin el argumento purge.

Ahora que todo esta listo debemos preparar el entorno para que se construya el producto ISO en el mismo directorio ejecute el siguiente comando:

`lb config --bootappend-live "boot=live components"  --distribution stable --debian-installer live --archive-areas "main contrib non-free"`

Despues de ejecutarlo se crearan en el directorio `config` muchos archivos especificos, de estos en el directorio `config` esta el directorio `package-list` y cada archivo alli indicara los programas a incluir, un nombre por linea. Este directorio dice que sera incluido, otros determinan y modifican el resultado final. Por ahora no es necesario modificar nada el comando ejecutado prepara el entorno para usar esas configuraciones.

Terminado las configuraciones y preparaciones ejecutemos el siguiente comando:

`lb build`

Este ultimo tomara un tiempo largo en ejecutar y en la consola saldran muchisimas lineas, y dependera de el tipo de disco duro y la velocidad de internet.

Al terminar se generaran muchos archivos en el directorio raiz donde el producto final es un archivo con extension `.iso` este es el sistema Debian live con las modificaciones.

Si se queire repetir el proceso el comando `lb clean` debe ejecutarse nuevamente pero sin el argumento "purge".

## DOCS

* [README inicial](../README.md) -
