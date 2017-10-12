---
layout: post
title: Grub2 - setting the default boot OS 
date: 2017-10-12
summary: Telling grub2 what OS to load by default
categories: lpic1
author: Ale-gargolario
image: /images/grub2_logo.png
tags:
 - lpic1
 - grub2
 - grep
 - cut
---

If we have more than one OS in our HD or SSD (either dual or multi boot) we may find ourselves in the scenario where, depending on a number of reasons, the default boot OS is not the one we want or changes when a major upgrade takes place. However we can tell **grub2** to boot always the same OS (to avoid changing it ourselves during **grub2**'s timeout screen). To do this, we have to check on **/boot/grub/grub.cfg** & do some tweaking on **/etc/default/grub**.


## Checking how many boot OS entries we have in <span style="color:darkblue">**/boot/grub/grub.cfg**</span>

We will run the following command (to grep the relevant information — *field \#2* in lines starting with *menuentry*):

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
As you can see, I have 3 OSs on my HD: **Zorin** (default), **Windows 7** and **Linux Mint 18.1 Serena**. Now let's suppose 
I want to make **Linux Mint** the new default ...


## Making a specific OS the default at boot in <span style="color:darkblue">**/etc/default/grub**</span>

The important parameter here is **GRUB_DEFAULT**. Let's grep **/etc/default/grub** for this parameter and its value:

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
It's a good practice to copy and paste the value from the output of **grep "^menuentry" /boot/grub/grub.cfg |cut -d "'" -f2**
to avoid spelling mistakes.

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

![_config.yml]({{ site.baseurl }}/images/grub2_logo.png)


#### Fuentes y recursos de interés:

**Grub2 Quick Start:** <https://wiki.gentoo.org/wiki/GRUB2_Quick_Start>

**GNU Grub Manual:** <https://www.gnu.org/software/grub/manual/grub/>
