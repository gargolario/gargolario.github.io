---
layout: post
title: Renombrar archivo añadiendo fecha
date: 2017-09-23
summary: Facilitando el manejo de archivos
categories: lpic1
author: Ale gargolario
image: /images/terminal.png
tags:
 - lpic1
 - bash
 - sustitución-de-comandos
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
+ Aparte de con el símbolo del dólar y los paréntesis (`$()`), la sustitución de comandos también puede implementarse con las comillas invertidas; de modo que el ejemplo anterior también podría haberse escrito de la siguiente forma:

```bash
mv archivo.png archivo.png.`date +%F`
```

Halof!!!

![_config.yml]({{ site.baseurl }}/images/terminal.png)
