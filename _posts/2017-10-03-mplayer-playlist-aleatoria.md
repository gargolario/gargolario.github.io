---
layout: post
title: find y mplayer para crear playlists y reproducirlas de forma aleatoria 
date: 2017-10-03
summary: Creación de playlists y reproducción aleatoria desde la terminal
categories: mplayer find
author: Ale gargolario
image: /images/mplayer.png
comments: true
tags:
 - find
 - mplayer
 - bash
 - playlist
---
Aunque hay infinidad de reproductores multimedia con interfaz gráfica, siempre me ha gustado la idea de un cómodo y frugal reproductor por línea de comandos. Ese reproductor se llama **mplayer**. En este post vamos a ver cómo podemos crear listas de reproducción y reproducirlas de forma aleatoria.

En primer lugar, utilizaremos el maravilloso comando **find** para buscar todos los archivos **.ogg** de nuestro **$HOME**:

## Búsqueda de archivos *.ogg* con *find* y redirección al archivo de texto *mi_playlist*
``` bash
find ~ -name "*.ogg" > mi_playlist
```
## Ahora utilizamos *mplayer* para reproducir la lista que acabamos de crear de forma aleatoria

``` bash
mplayer -playlist mi_playlist -shuffle
```
## Notas:
+ Si queremos reproducir de forma aleatoria toda la música que hay en un directorio (por ejemplo **~/Música**), basta con la siguiente orden:
```bash
mplayer ~/Música/* -shuffle

Halof!!!

![_config.yml]({{ site.baseurl }}/images/mplayer.png)
