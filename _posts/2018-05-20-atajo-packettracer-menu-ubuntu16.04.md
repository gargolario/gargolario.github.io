---
layout: post
title: Crear atajo a Packettracer en el menú de programas de Ubuntu 16.04
date: 2018-05-20
summary: Cómo lanzar el programa de simulación de redes de Cisco desde la GUI de Ubuntu 16.04
categories: cisco 
author: Ale gargolario
image: /images/packettracer.jpg
tags:
 - redes
 - cisco
 - osi
 - tcp
 - ubuntu
---

Packettracer es un programa de simulación de redes de [Cisco](https://www.cisco.com/) muy útil a la hora de realizar prácticas de topología de red.
Veamos cómo se instala en Ubuntu 16.04.

### Instalación de Packettracer7 en Ubuntu 16.04

En cuanto a distribuciones de GNU/Linux, al momento de escirbir esta publicación Packettracer está solo disponible para Ubuntu 14.04. No obstante, podemos instalarlo en Ubuntu 16.04 haciendo lo siguiente:

+ Descargamos la versión para Ubuntu 14.04.
+ Descargamos una librería extra y la instalamos:

```bash
wget http://ftp.br.debian.org/debian/pool/main/i/icu/libicu52_52.1-8+deb8u6_amd64.deb
sudo dpkg -i libicu52_52.1-8+deb8u6_amd64.deb
```
+ Instalamos el script **install** que viene con el programa.

Si todo ha ido bien ya tenemos el programa instalado y lo podemos ejecutar escribiendo `packettracer` en una terminal. Sin embargo, nosotros queremos crear un atajo en el menú de programas de la interfaz gráfica para poder lanzarlo desde ahí. Como es un programa muy divertido, lo incluiremos en el submenú **Juegos**.

### Creación de un atajo a Packettracer7 en menú de programas

Para ello creamos, activamos bit de ejecución y ejecutamos el siguiente script:

```bash
echo -e ' Name=Packettracer
 Terminal=false
 Categories=Game
 Type=Application'\\n \
Exec=~/.pt/packettracer\\n \
Icon=~/.pt/art/app.png > packettracer

cut -d' ' -f2 packettracer > /usr/share/applications/packettracer.desktop
sed -i '/Name=Packettracer/i [Desktop Entry]' /usr/share/applications/packettracer.desktop

```
Halof!

![_config.yml]({{ site.baseurl }}/images/packettracer.jpg) 

#### Notas
*** 
+ El script de creación del atajo también podríamos haberlo anexado al final del script de instalación y así hacerlo todo de una tacada.
+ Añadir que este tutorial también se puede aplicar a derivadas de Ubuntu; de hecho yo he realizado todos los pasos arriba mencionados en **Zorin OS 12.3 64-bit** con **GNOME Shell 3.18.5** y ha funcionado perfectamente.

**Web de Cisco:** <https://www.cisco.com/>

