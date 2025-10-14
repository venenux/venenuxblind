
#  Debian VENENUX Desktop

Este directorio construye un debian una imagen ISO/USB mix, como si de un disco duro se tratase, 
esta instalacion trae `openbox` y `mate` como escritorios.

This directory builds a debian image USB/ISO mixed, like a hard disk made, 
this installation comes with `openbox` and `mate` desktops.

## Requerimientos

* Debian estable
* 2018+ year pc
* 22Gb disco libre
* 60Kbps internet minimo
* 2GHz CPU minimo
* 2Gb swap minimo
* 2G RAM minimo

## Proceso

El proceso aqui esta descrito para una persona nivel medio y ademas ciega.

En la raiz de este repositorio (encima de este directorio docs) 
ejecute el comando `lb clean` para asegurar un inicio limpio.

Acto seguido se debe ejecutar la orden de configuracion, el comando 
siguiente lo hace usando parametros siempre estan en la rama estable:

`lb config --bootappend-live "boot=live components"  --distribution stable --debian-installer live --archive-areas "main contrib non-free"`

Despues se creara un directorio `config` con muchos archivos.

En el directorio `config` esta el directorio `package-list` y cada archivo alli 
indicara los programas a incluir, un nombre por linea. Este directorio dice 
que sera incluido, otros determinan y modifican el resultado final.

Una vez editados los archivos ejecutar el comando `lb build` este tomara un 
tiempo largo en ejecutar y en la consola saldran muchisimas lineas.

Al terminar se generaran muchos archivos donde el producto final es un archivo 
con extension `.iso` este es el sistema Debian live con las modificaciones.

## DOCS

* [README inicial](../README.md) -
