---
layout: post
title: Renombrar archivo añadiendo fecha
date: 2017-9-23
categories: bash
---
Una buena forma de no confundirnos con versiones de un mismo archivo es incluir la fecha de modificación/creación de dicho archivo en su propio nombre. Para ello, podemos utilizar el siguiente comando:

``` bash
mv archivo.png archivo.png.$(date +%F)
```
Esto daría como resultado **archivo.png.2017-09-23**
