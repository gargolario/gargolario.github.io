---
layout: post
title: Monitorizar temperaturas de CPU y GPU NVIDIA en GNU/Linux
date: 2019-04-19
summary: Controla que las temperaturas más importantes de tu ordenador están dentro de rangos deseables
categories: miscelánea
author: Ale gargolario
image: /images/terminal-suse.png
tags:
- cpu
- temperatura
- gpu
- watch
- nvidia
---

Si le das bastante caña a tu ordenador con **GNU/Linux** (bien por que te guste jugar, bien porque diseñes), seguro que te habrás preguntado cuánto pueden llegar a calentarse la tarjeta gráfica o el procesdor.

Pues bien, en la presente entrada de blog veremos un par de comandos para monitorizar (vía terminal) las temperaturas de CPU y de GPU. En ambos casos usaremos el comando **watch**, que sirve para realizar medidas con la frecuencia (en segundos) que nosostros le indiquemos. Si no lo tienes ya disponible en tu sistema, deberás instalar el paquete `lm-sensors` y ejecutar -- con `sudo` -- el comando `sensors-detect`.

### Temperatura de CPU

```bash
watch sensors
```

Lo cual nos dará algo similar a lo siguiente (y se irá actualizando cada 2 segundos):

```bash
(...)coretemp-isa-0000
Adapter: ISA adapter
Package id 0:  +35.0°C  (high = +82.0°C, crit = +100.0°C)
Core 0:        +32.0°C  (high = +82.0°C, crit = +100.0°C)
Core 1:        +33.0°C  (high = +82.0°C, crit = +100.0°C)
Core 2:        +31.0°C  (high = +82.0°C, crit = +100.0°C)
Core 3:        +32.0°C  (high = +82.0°C, crit = +100.0°C)
Core 4:        +35.0°C  (high = +82.0°C, crit = +100.0°C)
Core 5:        +32.0°C  (high = +82.0°C, crit = +100.0°C)
```

La salida anterior nos permite ver la temperatura en tiempo real de cada uno de los 6 núcleos del procesador. Asi mismo, se nos informa tanto de los valores altos (`+82.0ºC`) como de los críticos (`+100.0ºC`).

### Temperatura de GPU Nvidia

Para disponer de la utilidad que vamos a utilizar (`nvidia-smi`) debes instalar el driver de Nvidia en tu distribución. Una vez lo hayas hecho, lanzaremos el siguiente comando:

```bash
watch nvidia-smi
```
Obtendremos algo similar a esto (también cada 2 segundos):

```bash
(...)
Sun Oct 27 11:12:11 2019
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 430.40       Driver Version: 430.40       CUDA Version: 10.1     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  GeForce GTX 106...  Off  | 00000000:01:00.0  On |                  N/A |
| 24%   54C    P8     9W / 120W |    422MiB /  6077MiB |     13%      Default |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|    0      1307      G   /usr/lib/xorg/Xorg                           211MiB |
|    0      1455      G   /usr/bin/gnome-shell                         152MiB |
|    0      3185      G   ...equest-channel-token=(...)                 56MiB |
+-----------------------------------------------------------------------------+

```
Aparte de la versión del driver (`430.40`) y de CUDA (`10.1`) podemos ver la información relativa al ventilador (`24%`), el wattage, la memoria (`422MiB`), la utilización (13%) y los procesos activos (con PIDs `1307`, `1455` y `3185`).

Bueno, espero que te sea de utilidad.

Halof!

![_config.yml]({{ site.baseurl }}/images/terminal-suse.png)

#### Notas y otros comandos interesantes

+ Para comprobar qué tarjeta gráfica tienes instalada: `lspci -v |grep VGA`

+ Ver drivers disponibles para tu tarjeta gráfica en Ubuntu y derivadas: `sudo ubuntu-drivers list` y `sudo ubuntu-drivers devices`

+ La frecuencia de actualización del comando `watch` (2 segundos por defecto) se puede modificar con la opción `-n` y el número de segundos que deseemos (eg: `-n 4`).

+ CUDA es el acrónimo de _Compute Unified Device Architecture_ (_Arquitectura Unificada de Dispositivos de Cómputo_). Se trata de una plataforma creada por Nvidia que incluye un compilador y otras herramientas para que, usando una variación del lenguaje C, los programadores codifiquen algoritmos en las GPU.

+ Otra publicación similar en **It's Foss**: <https://itsfoss.com/monitor-cpu-gpu-temp-linux/>

