---
layout: post
title: Módulo exfat-nofuse para usar Vitashell en Ubuntu xenial vía USB
date: 2018-07-14
summary: Compila el módulo y conecta tu consola por USB a GNU/Linux
categories: zorin 
author: Ale gargolario
image: /images/vita.png
tags:
 - psvita
 - zorin
 - exfat-nofuse
 - ubuntu
---

[Vitashell](https://github.com/TheOfficialFloW/VitaShell/releases/) es un fantástico gestor de archivos para **PSVita** que nos permite conectar nuestra consola a nuestro ordenador vía **FTP** o **USB**. Si eres usuario de **Ubuntu 16.04 Xenial**, **Zorin 12.3** (o cualquier otra derivada) y estás teniendo problemas a la hora de montar el sistema de archivos de la Vita por USB, probablemente sea porque necesites compilar e instalar el módulo **exfat-nofuse**. Si es así, sigue leyendo para solucionarlo: 


### Descargamos las utilidades necesarias para descargar y compilar

```bash
sudo apt-get install build-essential git linux-headers
```

### Clonamos el repositorio exfat-nofuse

```bash
git clone https://github.com/rxrz/exfat-nofuse.git
```

### Nos movemos a él

```bash
cd exfat-nofuse/
```
### Nos hacemos **root**

```bash
sudo su
```
### Compilamos e instalamos el módulo

```bash
make && make install
```

### Volvemos a nuestro usuario normal

```bash
exit
```
### Desinstalamos los paquetes **exfat-fuse** y **exfat-utils** (módulo y utilidades respectivamente) para evitar conflictos 

```bash
sudo apt-get remove exfat-fuse exfat-utils
```

### Cargamos el módulo que hemos compilado

```bash
sudo modprobe exfat
```
¡Ya puedes conectar tu consola y empezar a gestionar archivos!


Halof!!!


![_config.yml]({{ site.baseurl }}/images/vita.png)

#### Notas:
+ Para tener el módulo cargado cada vez que reiniciemos nuestro ordenador podemos utilizar la siguiente orden:

```bash
echo exfat | sudo tee -a /etc/modules-load.d/exfat.conf
```
#### Referencias
***

+ https://github.com/TheOfficialFloW/VitaShell/issues/178
+ https://gbatemp.net/threads/vita-shell-1-5-usb-on-linux-ubuntu.458713/
