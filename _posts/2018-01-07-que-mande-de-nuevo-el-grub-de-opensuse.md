---
layout: post
title: Que mande de nuevo el grub de openSuSE
date: 2018-01-07
summary: Reinstalar el grub de opensuse en el MBR vía YaST para arranques duales
categories: opensuse 
author: Ale gargolario
image: /images/aardvark-yast.png
tags:
 - opensuse
 - yast
 - arranque dual
---

Aparte de mi querido **openSUSE**, mi disco duro suele dar cobijo a otras distribuciones como, por ejemplo, la bella [**ZorinOS**](https://zorinos.com/) (derivada de **Ubuntu**). Y a veces ocurre que, por el motivo que sea, la última distro que instalamos instala su **grub** en el **MBR** y nuestro bonito **grub** de **openSuSE** desaparece.
En este post vamos a ver cómo solucionar esta situación volviendo a instalar **grub** en el MBR vía **YaST**:


### Reinstalación de grub en el MBR con YaST

Buscamos **YaST** en el tablero de mandos:
![config.yml]({{ site.baseurl }}/images/Yast_reinstall_grub01.png)

Tras introducir nuestra contraseña de **root**, vamos a **Sistema > Cargador de arranque**:

![config.yml]({{ site.baseurl }}/images/Yast_reinstall_grub02.png)

Una vez dentro, tenemos que marcar la opción **Escribir código de arranque genérico en el MBR** y aceptar*:

![config.yml]({{ site.baseurl }}/images/Yast_reinstall_grub03.png)


Ya está: la próxima vez que arranquemos nuestro equipo será el **grub** de **openSuSE** el que nos dé la bienvenida.


Halof!!!


![_config.yml]({{ site.baseurl }}/images/aardvark-yast.png)

#### Notes:
+ *Si la opción **Escribir código genérico de arranque en el MBR** estaba ya marcada, la desmarcamos, la volvemos a marcar y aceptamos.

#### References
***

**openSUSE Leap 42.3 Documentation:** https://doc.opensuse.org/documentation/leap/reference/html/book.opensuse.reference/cha.grub2.html
