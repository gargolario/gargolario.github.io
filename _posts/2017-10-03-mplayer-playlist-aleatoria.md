---
layout: post
title: find y mplayer para crear playlists y reproducirlas de forma aleatoria 
date: 2017-10-03
summary: Creación de playlists y reproducción aleatoria desde la terminal
categories: mplayer lpic1
author: Ale gargolario
image: /images/mplayer.png
tags:
 - find
 - lpic1
 - mplayer
 - bash
 - playlist
---
Aunque hay infinidad de reproductores multimedia con interfaz gráfica, siempre me ha gustado la idea de un práctico y frugal reproductor por línea de comandos. Ese reproductor se llama [**mplayer**](http://www.mplayerhq.hu/design7/news.html) y te permite gestionar tu música (y vídeos) de forma muy cómoda desde la terminal. En este post vamos a ver cómo podemos crear listas de reproducción y reproducirlas de forma aleatoria.

En primer lugar, utilizaremos el maravilloso comando **find** para buscar todos los archivos **.ogg** de nuestro **$HOME** y crear la lista de reproduccón **mi_playlist**:

### Búsqueda de archivos *.ogg* con *find* y redirección al archivo de texto *mi_playlist*
``` bash
find ~ -name "*.ogg" > mi_playlist
```
Ahora utilizamos **mplayer** para reproducir la lista que acabamos de crear de forma aleatoria:

### Reproducción de forma aleatoria de la playlist
``` bash
mplayer -playlist mi_playlist -shuffle
```
#### Notas:
+ Si queremos reproducir de forma aleatoria toda la música que hay en un directorio (por ejemplo **~/Música**), basta con la siguiente orden:
```bash
mplayer ~/Música/* -shuffle
```
+ Mplayer también dispone de *GUIs* como, por ejemplo, [**SMplayer**](http://www.smplayer.info/).

Halof!!!

[![_config.yml]({{ site.baseurl }}/images/mplayer.png)](http://www.mplayerhq.hu/design7/news.html)

#### Fuentes y recursos de interés
*** 

**Web de Mplayer:** <http://www.mplayerhq.hu/design7/news.html>

**Web de SMplayer:** <http://www.smplayer.info/>
