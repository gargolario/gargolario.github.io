---
layout: post
title: grep en PDF
date: 2018-04-14
summary: Contar las ocurrencias de una palabra en un archivo PDF
categories: lpic1 
author: Ale gargolario
image: /images/terminal-suse.png
tags:
 - lpic1
 - pdf
---

En este post vamos a ver cómo utilizar el potencial de **grep** en archivos **PDF**.

## Comprobar que tenemos instalado el programa **pdftotext** que convierte PDFs a archivos de texto plano:

```bash
which pdftotext
```
Si no lo tenemos instalado, tendremos que instalar el paquete `poppler-tools` con el gestor de paquetes de nuestra distro (*apt*, *zypper*, etc.).
Con el paquete instalado, ya podemos contar ocurrencias en un PDF. 

## Contar ocurrencias en archivo PDF

Supongamos, por ejemplo, que tenemos una lista muy larga (llamada "lista-larga.pdf") con nombres y queremos saber de forma eficiente cuántas veces aparece el apellido "Abellán":

```bash
pdftotext lista-larga.pdf - |grep 'Abellán' |wc -l
```
Como puede verse, convertimos *lista-larga.pdf* a PDF, pero, en lugar de escribir el resultado a un archivo, se lo enviamos a *grep* mediante tubería y finalmente a *wc* para hacer el recuento.

Espero que este post haya sido de tu agrado y te haya servido.

Halof!!!


![_config.yml]({{ site.baseurl }}/images/terminal-suse.png)

#### Recursos de interés
*** 

**Manual de grep**:** <https://www.gnu.org/savannah-checkouts/gnu/grep/manual/grep.html>
