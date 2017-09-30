---
layout: post
title: Comprobar los últimos programas instalados en openSUSE
date: 2017-9-30
summary: Ver por consola los últimos paquetes instalados en openSuSE
categories: zypper opensuse rpm
author: Ale gargolario
image: /images/terminal-suse.png
tags:
 - opensuse
 - rpm
 - zypper
---


En este post vamos a ver, de dos formas diferentes, cómo comprobar por consola cuáles han sido los últimos programas 
que hemos instalado en nuestro openSUSSE.

### 1) Hacemos un cat al archivo /var/log/zypp/history

```bash
cat /var/log/zypp/history
```

### Y obtenemos el siguiente resultado

```bash
350317692dff15cdd6288|
2017-09-30 13:15:08|install|python3-speechd|0.8.3-6.7|x86_64||repo-oss|13f6d4ac909a546ae90f2fe30b22025a8cba88a4|
2017-09-30 13:15:09|install|mumble|1.2.17-1.2|x86_64|root@linux-672f|repo-oss|d4a130b1cb911b69784827073ca5588a40753c6c|
2017-09-30 13:15:10|install|speech-dispatcher|0.8.3-6.7|x86_64||repo-oss|7bc1b9e4d706630e780876e3a0ee51a798ed9a4f|
2017-09-30 13:15:10|install|speech-dispatcher-module-espeak|0.8.3-6.7|x86_64||repo-oss|99fc3f98ae4b67c2b6f08e36433c21a3151cea94| 
```
### 2) Utilizamos una orden rpm

```bash
rpm -qa --last | head 
```

### Y obtenemos el siguiente resultado

```bash
speech-dispatcher-module-espeak-0.8.3-6.7.x86_64 sáb 30 sep 2017 13:15:10 CEST
speech-dispatcher-0.8.3-6.7.x86_64            sáb 30 sep 2017 13:15:09 CEST
mumble-1.2.17-1.2.x86_64                      sáb 30 sep 2017 13:15:09 CEST
python3-speechd-0.8.3-6.7.x86_64              sáb 30 sep 2017 13:15:08 CEST
mumble-32bit-1.2.17-1.2.x86_64                sáb 30 sep 2017 13:15:08 CEST
```

Halof!!!


[![_config.yml]({{ site.baseurl }}/images/terminal-suse.png)]

## Notas:
+ Los argumentos **-qa** significan *query all*.
+ En **rpm -qa --last | head** usamos la tubería hacia **head** para obtener las primeras líneas de la salida del comando,
es decir, lo último que hemos instalado.
