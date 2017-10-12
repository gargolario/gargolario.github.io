---
layout: post
title: Grub2 - setting the default boot OS 
date: 2017-10-07
summary: Telling grub2 what OS to load by default
categories: lpic1
author: Ale-gargolario
image: /images/grub2.jpg
tags:
 - lpic1
 - grub2
 - grep
 - cut
---

If we have more than one OS in our HD or SSD (either dual or multi boot) we may find ourselves in the scenario where, depending on 
a number of reasons, the default boot OS is not the one we want or changes when a major upgrade takes place. However, we can
tell **grub2** to boot always the same OS. To do this, we have to use two files: **/boot/grub/grub.cfg** & **/etc/
default/grub**.


## Checking what OSs are available at boot (/boot/grub/grub.cfg)

We will run the following command:

```bash
grep "^menuentry" /boot/grub/grub.cfg |cut -d "'" -f2
```
Here's the output I obtained:

```bash
Zorin
Memory test (memtest86+)
Memory test (memtest86+, serial console 115200)
Windows Recovery Environment (loader) (en /dev/sda1)
Windows 7 (loader) (en /dev/sda3)
Linux Mint 18.1 Serena (18.1) (en /dev/sda5)
```
As you can see, I have 3 OSs on my HD: **Zorin** (default), **Windows 7** and **Linux Mint 18.1**. Now let's suppose 
I want to make **Linux Mint** the default ...


## Making a specific OS the default at boot (/etc/default/grub)

The important parameter here is **GRUB_DEFAULT=**. Let's grep **/etc/default/grub** for this parameter and its value:

```bash
grep GRUB_DEFAUL /etc/default/grub
```

We get the following output:

```bash
GRUB_DEFAULT=0
```
Than means **Zorin** — being the main OS — is also the boot default. Now to set **Linux Mint** as the new boot default, we
have to use our favourite text editor and change the value of **GRUB_DEFAULT** as follows:

```bash
GRUB_DEFAULT="Linux Mint 18.1 Serena (18.1) (en /dev/sda5)"
```
It's good

The only thing left to do now is updating **grub2** with:

```bash
sudo update-grub
```
or ...

```bash
sudo update-grub2
```
.. .since **update-grub2** is linked to **update-grub**

Halof!!!

![_config.yml]({{ site.baseurl }}/images/grub2.jpg)

#### Notas:
+ El argumento **-i** indica el archivo que **ffmpeg** toma como **input**, es decir, *video_musical.mp4*.
+ El **%4d** expande el nombre de los archivos resultantes a **foto** + *4 dígitos* + **.jpg**, es decir, *foto0001.jpg*, *foto0002.jpg*, etc.

#### Fuentes y recursos de interés:

**Grub2 Quick Start:** <https://wiki.gentoo.org/wiki/GRUB2_Quick_Start>

**GNU Grub Manual:** <https://www.gnu.org/software/grub/manual/grub/>
