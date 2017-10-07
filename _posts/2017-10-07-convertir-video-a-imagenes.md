---
layout: post
title: Convertir vídeo a imágenes con ffmpeg
date: 2017-10-07
summary: Extrae imágenes de un vídeo por consola
categories: miscelánea
author: Ale gargolario
image: /images/FFmpeg.png
tags:
 - ffmpeg
 - bash
 - file-globbing
---

A veces me gusta extraer imágenes de algún clip musical. Una forma cómoda y rápida de hacerlo es por medio de nuestra 
querida terminal. 

Supongamos que tenemos el archivo *video_musical.mp4* y lo queremos convertir a archivos **jpg** para, posteriormente, 
seleccionar las que más nos gusten. Veamos cómo hacerlo con la herramienta [**FFmpeg**](https://www.ffmpeg.org/):


## Conversión de un archivo de vídeo a imágenes estáticas

```bash
ffmpeg -i video_musical.mp4 foto%4d.jpg
```
Ya está; una vez terminado el proceso podemos ver todas las fotos con **ls** o con nuestro navegador de archivos.

Halof!!!

[![_config.yml]({{ site.baseurl }}/images/FFmpeg.png)](https://www.ffmpeg.org/)

#### Notas:
+ El argumento **-i** indica el archivo que **ffmpeg** toma como **input**, es decir, *video.musical.mp4*.
+ El **%4d** expande el nombre de los archivos resultantes a **foto** + *4 dígitos* + **.jpg**, es decir, *foto0001.jpg*, *foto0002.jpg*, etc.

#### Fuentes y recursos de interés:

**Web de FFmpeg:** <https://www.ffmpeg.org/>
