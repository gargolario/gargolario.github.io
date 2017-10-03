---
layout: post
title: dpkg & rpm - descubrir a qué paquete pertenece un archivo
date: 2017-10-3
summary: ¿Qué paquete instaló qué archivo?
categories: dpkg rpm
author: Ale gargolario
image: /images/terminal-suse.png
tags:
 - dpkg
 - rpm
 - bash
---

En las labores de mantenimiento de nuestros sistemas **GNU/Linux**, a menudo nos encontramos con la necesidad de saber
de qué paquete proviene un determinado archivo de configuración (o de cualquier otro tipo).

En este post vamos a ver cómo podemos averiguar eso mismo: qué paquete instaló qué archivo en nuestra máquina. Y lo vamos
a hacer con los dos gestores de paquetería más populares en el mundo del software libre: **dpkg** y **rpm**.

### dpkg (Debian, Ubuntu, Linux Mint, Zorin, ...)
#### ¿Qué paquete instaló pam.conf?
```bash
ale@ale-Aspire-1810TZ:~$ dpkg --search /etc/pam.conf 
libpam-runtime: /etc/pam.conf
```
El comando **dpkg --search** nos indica que el archivo **pam.conf** fuen instalado en el sistema con el paquete **libpam-runtime**. 

### rpm (Red Hat, openSUSE, centOS, ...)
#### ¿Qué paquete instaló crontab?
```bash
[slimbook@linux-2ra3 ~]$ rpm -qf /etc/crontab 
cronie-1.4.11-58.25.x86_64
```
El comando **rpm -qf** nos indica que el archivo **crontab** fue instalado en el sistema con el paquete **cronie-1.4.11-58.25.x86_64**. 

Halof!!!


![_config.yml]({{ site.baseurl }}/images/terminal-suse.png)

#### Notas:
+ **dpkg** significa **Debian GNU/Linux Package Manager**.
+ **rpm** significó inicialmente **Red Hat Package Manager** y después se transformó en el acrónimo recursivo
**RPM Package Manager**.
