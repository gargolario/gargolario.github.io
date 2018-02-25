---
layout: post
title: Rstudio - Knit a PDF en Zorin 12.2
date: 2018-11-25
summary: Pasos a seguir para poder exportar archivos Rmd a PDF
categories: programación zorin
author: Ale gargolario
image: /images/R_logo.svg.png
tags:
 - R
 - zorin
 - knit a pdf
---

El [IDE RStudio](https:www.rstudio.com) nos permite hacer algo muy chulo: exportar archivos *Rmarkdown* a *PDF* (también a *HTML* y a *docx*). En **Zorin 12.2**, **Ubuntu 16.04** y otras derivadas de esta última podemos encontrarnos algún error debido a que nos falta instalar algo. Esa ha sido la motivación para escribir este post. Vamos a ello:

### Lo primero es instalar LaTeX:

``` bash
sudo apt-get install texlive
```
#### Si tras intentar *knit to PDF* encontramos el error `pandoc document conversion failed with error 43`, hacemos lo siguiente:

1. en **RStudio** vamos a **packages > install packages > devtools**

2. en la consola de **RStudio** escribimos **devtools::install_github("rstudio/rmarkdown")**

##### Si encontramos el error `Error in library(devtools) : there is no package called ‘devtools’`, abrimos una terminal y escribimos:

``` bash
sudo apt-get install libcurl4-openssl-dev libssl-dev
```
### Últimos pasos:

Ahora, cuando intentemos exportar a PDF, es posible que encontremos el siguiente error `Error: failed to compile nuestro_archivo.tex. See nuestro_archivo.log for more info` y, al comprobar el log, leamos `! LaTeX Error: File \`lmodern.sty' not found.`

Instalamos lo que falta en la terminal:

``` bash
sudo apt-get install lmodern
```

Si, después de todo esto, encontramos otro error de LaTeX `! LaTeX Error: File \`framed.sty' not found`, procedemos con:

``` bash
sudo apt-get install texlive-latex-extra
```
Cerramos y abrimos RStudio y ahora deberíamos poder exportar a PDF sin problemas.

Halof!!!

![_config.yml]({{ site.baseurl }}/images/R_logo.svg.png)

#### Recursos de interés
*** 

 Web de R <https://www.r-project.org/>

 Web de RStudio <https://www.rstudio.com/>
