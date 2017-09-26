---
layout: post
title: Habilitar enrutamiento en Linux
date: 2017-9-23
categories: lpic2
---

La función de enrutamiento está integrada de forma nativa en el núcleo Linux, es decir, cualquier sistema GNU/Linux es un
router en potencia. Ahora bien, esta funcionalidad viene desactivada por defecto; para activarla debemos ir al sistema de
archivos virtual **/proc** y cambiar el valor de un bit de 0 a 1. La ruta exacta es **/proc/sys/net/ipv4/ip_forward**.

Esto podemos hacerlo de 3 formas:

## Método 1 (no persistente)
***
Mandamos un 1 al archivo virtual **ip_forward**:

```bash
echo 1 > /proc/sys/net/ipv4/ip_forward
```


## Método 2 (no persistente)
***
El comando **sysctl** modifica dinámicamente los parámetros del kernel Linux que cuelgan de **/proc/sys**, por lo tanto,
sustituyendo las barras (**/**) por puntos (**.**), podemos cambiar el valor del bit de la siguiente forma:


```bash
sysctl net.ipv4.ip_forward=1
```

## Método 3 (persistente) 
***
Escribimos directamente el 1 en el archivo **/etc/sysctl.conf**:

```bash
net.ipv4.ip_forward=1
```
La persistencia hace referencia a si el valor se pierde en cada reinicio del sistema. Como hemos visto, de los 3 métodos, el
único que nos garantiza el bit a 1 con los reinicios el nº3.


Halof!!!

[![_config.yml]({{ site.baseurl }}/images/logo@2x.png)](https://www.lpi.org)


