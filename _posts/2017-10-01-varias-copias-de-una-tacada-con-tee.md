---
layout: post
title: Hacer múltiples copias de un archivo con tee
date: 2017-10-01
summary: Cómo hacer múltiples copias de un archivo de una tacada 
categories: lpic1
author: Ale gargolario
image: /images/terminal-suse.png
tags:
 - bash
 - tee
 - redirección
 - ['expansión de llaves']
 - lpic1
---
El comando **tee** tiene de particular que lee desde la entrada estándar (**stdin**) y escribe tanto a la salida estándar
(**stdout**) como a un archivo de forma simultánea. 

Nosotros vamos a hacer uso del redireccionamiento (**<** y **>**) para hacer varias copias de un mismo archivo de una tacada.
Veamos cómo suponiendo que el archivo del que queremos hacer copias es una foto llamada **foto.png** y que queremos hacer 
7 copias:

``` bash
tee < foto.png > /dev/null foto{1..7}.png
```
Esto daría como resultado:

``` bash
foto1.png foto2.png foto3.png foto4.png foto5.png foto6.png foto7.png
```
#### Notas:
+ En lugar de leer desde **stdin**, el primer redireccionamiento (**<**) le permite a **tee** leer desde el archivo **foto.png**.
+ El segundo redireccionamiento (**>**) envía simultáneamente la salida a **/dev/null** (para evitar ver un montón de símbolos
binarios inentiligibles por **stdout**, es decir, por pantalla) y al archivo **foto{1..7}.png** que, en realidad, no es un archivo
sino 7 - gracias a la expansión de llaves o *brace expansion* (**{1..7}**).

Halof!!!

![_config.yml]({{ site.baseurl }}/images/terminal-suse.png)
