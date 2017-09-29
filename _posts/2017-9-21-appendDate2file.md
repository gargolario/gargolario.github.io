---
layout: post
title: Renombrar archivo añadiendo fecha
date: 2017-9-23
summary: Facilitando el manejo de archivos
categories: bash
author: Ale gargolario
image: /images/terminal.png 
tags:
 - bash

---
Una buena forma de no confundirnos con versiones de un mismo archivo es incluir la fecha de modificación/creación de dicho archivo en su propio nombre. Para ello, podemos utilizar la siguiente orden:

``` bash
mv archivo.png archivo.png.$(date +%F)
```
Esto daría como resultado:

``` bash
archivo.png.2017-09-23
```
Halof!!!

![_config.yml]({{ site.baseurl }}/images/terminal.png)
