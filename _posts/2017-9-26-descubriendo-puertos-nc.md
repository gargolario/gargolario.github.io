---
layout: post
title: Descubriendo puertos abiertos con nc
date: 2017-9-26
categories: bash lpic2
---
Una forma rápida y eficaz de comprobar qué puertos tiene abiertos un sistema consiste en usar el comando **nc**.
Supongamos que queremos saber si la máquina con IP 192.168.1.12 de nuestra red local tiene un servidor web activo
en el puerto estándar. Procederemos de la siguiente forma:

``` bash
nc -vz 192.168.1.12 80
```
En caso afirmativo, veríamos por pantalla el siguiente resultado:

``` bash
Connection to 192.168.1.12 80 port[tcp/http] succeeded!
```

## Notas:
+ La opción **-v** proporciona verbosidad.
+ La opción **-z** le indica a **nc** que compruebe la conexión, sin enviar datos.

Halof!!!

[![_config.yml]({{ site.baseurl }}/images/logo@2x.png)](https://www.lpi.org)
