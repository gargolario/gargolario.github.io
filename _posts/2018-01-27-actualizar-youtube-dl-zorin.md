---
layout: post
title: Actualizar youtube-dl a la última versión en Zorin 12
date: 2018-01-27
summary: Cómo actualizar youtube-dl sin problemas a la última versión en derivadas de Ubuntu
categories: zorin
author: Ale gargolario
image: /images/zorin.png
tags:
 - zorin
 - ubuntu
 - youtube-dl
---

A veces ocurre que intentamos descargar vídeos con el magnífico programa **youtube-dl** en la bella distro irlandesa **ZorinOS** y nos da error debido a que la versión que tenemos no está actualizda. Probamos con ``youtube-dl -U`` y/o actualizamos a la útlima versión de los repositorios de **Ubuntu** y nada de nada.

La solución pasa por descargarse la última versión de la web de [youtue-dl](https://yt-dl.org/latest/youtube-dl):

``` bash
sudo curl -L https://yt-dl.org/latest/youtube-dl -o /usr/bin/youtube-dl
```
Y cambiarle los permisos:

``` bash
sudo chmod 755 /usr/bin/youtube-dl
```
Pues, venga, a descargar ese vídeos bonitos, ;)

Halof!!!

![_config.yml]({{ site.baseurl }}/images/zorin.png)

#### References
*** 

 Apache wiki: <https://yt-dl.org>
 Web de Zorin: <https://zorinos.com/>
