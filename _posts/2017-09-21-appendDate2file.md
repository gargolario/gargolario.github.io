---
layout: post
title: Renombrar archivo añadiendo fecha
date: 2017-09-23
summary: Facilitando el manejo de archivos
categories: miscelánea
author: Ale gargolario
image: /images/terminal.png
tags:
 - terminal
 - bash
 - sustitución de comandos
---

Una buena forma de no confundirnos con versiones de un mismo archivo es incluir la fecha de modificación/creación de dicho archivo en su propio nombre. Para ello, podemos hacer uso de la sustitución de comandos.

### Sustitución de comandos para renombrar archivo añadiendo fecha

``` bash
mv archivo.png archivo.png.$(date +%F)
```
Esto daría como resultado:

``` bash
archivo.png.2017-09-23
```

#### Notas:
+ La sustitución de comandos, `$(date +%F)`, también puede implementarse con 
```bash
`date +%F`
```. 

Halof!!!

![_config.yml]({{ site.baseurl }}/images/terminal.png)
