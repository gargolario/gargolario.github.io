---
layout: post
title: service, un solo comando para ver todos los servicios
date: 2017-10-14
summary: Una forma práctica de comprobar qué servicios están activos en nuestro servidor
categories: lpic2
author: Ale gargolario
image: /images/terminal-suse.png
tags:
 - lpic2
 - service
 - servicios
 - systemd
 - system V
---

Aún con la llegada de **systemd**, el programa **service** sigue estando presente en la mayoría de distribuciones **GNU/Linux**. Su misión es la de **arrancar**, **recargar** o **parar** los scripts de inicio de **System V**. Sin embargo, este comando también tiene una opción de consulta muy útil para comprobar el estado de todos los servicios disponibles en nuestro servidor. De eso mismo es de lo que hablaremos en el post de hoy.

### Comprobación del estado de los servicios de nuestro servidor

```bash
service --status-all
```
Veamos qué se nos muestra por salida estándar:

```bash
 [ + ]  acpid
 [ - ]  alsa-utils
 [ + ]  anacron
 [ + ]  apparmor
 [ + ]  apport
 [ + ]  avahi-daemon
 [ + ]  binfmt-support
 [ - ]  bluetooth
 [ - ]  bootmisc.sh
 [ - ]  brltty
 [ - ]  checkfs.sh
 [ - ]  checkroot-bootclean.sh
 [ - ]  checkroot.sh
 [ + ]  console-setup
 [ + ]  cron
 [ + ]  cups
 [ + ]  cups-browsed
 [ + ]  dbus
 [ + ]  gdm3
 [ + ]  grub-common
 [ - ]  hostname.sh
 [ - ]  hwclock.sh
 [ + ]  irqbalance
 [ - ]  kerneloops
 [ + ]  keyboard-setup
 [ - ]  killprocs
 [ + ]  kmod
 [ - ]  mountall-bootclean.sh
 [ - ]  mountall.sh
 [ - ]  mountdevsubfs.sh
 [ - ]  mountkernfs.sh
 [ - ]  mountnfs-bootclean.sh
 [ - ]  mountnfs.sh
 [ + ]  network-manager
 [ + ]  networking
 [ + ]  ondemand
 [ + ]  openvpn
 [ - ]  plymouth
 [ - ]  plymouth-log
 [ - ]  pppd-dns
 [ + ]  procps
 [ + ]  rc.local
 [ + ]  resolvconf
 [ - ]  rpcbind
 [ - ]  rsync
 [ + ]  rsyslog
 [ - ]  saned
 [ - ]  sendsigs
 [ + ]  speech-dispatcher
 [ - ]  ssh
 [ - ]  thermald
 [ + ]  udev
 [ + ]  ufw
 [ - ]  umountfs
 [ - ]  umountnfs.sh
 [ - ]  umountroot
 [ + ]  unattended-upgrades
 [ + ]  urandom
 [ - ]  uuidd
 [ + ]  virtualbox
 [ + ]  whoopsie
 [ - ]  x11-common
```
Vemos, por ejemplo, como el demonio de *interfaz avanzada de configuración y energía* (**acpid**) está activo; como también lo están el de *tareas **cron*** o el *servidor de impresión **cups***. Por el contrario, nuestro *servidor **ssh*** y nuestro *servidor de escáneres (**saned**)*, por citar solo un par, están inactivos.

### Explicación del funcionamiento y resumen

**/usr/sbin/service** busca el estado de los servicios en los scripts de **/etc/init.d/**. En función de lo que encuentre en
las líneas de esos scripts, pueden darse tres casos:

+ Si **[ + ]** precede al nombre del servicio, el servicio está funcionando.

```bash
[ + ]  whoopsie
```

+ Si **[ - ]** precede al nombre del servicio, el servicio no está funcionando.

```bash
[ - ]  whoopsie
```

+ Si **[ ? ]** precede al nombre del servicio, el programa **service** no puede determinar la línea de estado del servicio en el script correspondiente de **/etc/init.d/**.

**eg**: 
```bash
[ ? ]  whoopsie
```

Halof!!!


![_config.yml]({{ site.baseurl }}/images/terminal-suse.png)


