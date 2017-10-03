---
layout: post
title: Fusionar imágenes con Imagemagick
date: 2017-9-28
summary: Trabajando imágenes desde la terminal
image: /images/imagemagick.jpg
categories: imagemagick 
author: Ale gargolario
image: /images/imagemagick.jpg
tags: 
 - imagemagick
 - bash
---

Si queremos fusionar dos o más imágenes en una, podemos recurrir a la terminal y usar el comando **convert** del paquete de software
**ImageMagick**. Este paquete sirve para crear, editar, componer y convertir imágenes de mapas de bit y suele venir instalado por 
defecto en nuestra distribución GNU/Linux favorita.

Imaginemos que estamos dentro del directorio **imagenes_jpg**, que contiene tres imágnes (**imagen1.jpg imagen2.jpg imagen3.jpg**). 
Bien, pues manos a la obra:

### Fusionar 3 imágenes verticalmente

#### Sin uso de comodín

```bash
convert imagen1.jpg imagen2.jpg imagen3.jpg -append imagen123.jpg 
```
#### Con uso de comodín

```bash
convert *.jpg -append imagen123.jpg 
```


### Fusionar 3 imágenes horizontalmente

#### Sin uso de comodín

```bash
convert imagen1.jpg imagen2.jpg imagen3.jpg +append imagen123.jpg 
```
#### Con uso de comodín

```bash
convert *.jpg +append imagen123.jpg 
```

Pues hala, a disfrutar fusionando!

Halof!!!


[![_config.yml]({{ site.baseurl }}/images/imagemagick.jpg)](https://www.imagemagick.org)

#### Notas:
+ La opción **-append** coloca las imágenes verticalmente.
+ La opción **+append** coloca las imágenes horizontalmente.

#### Fuentes
*** 

**Web de imagemagick:** <https://www.imagemagick.org>
