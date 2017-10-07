---
layout: post
title: Mofificando el estado de un repositorio con zypper
date: 2017-9-28
summary: Control de repositorios con zypper
categories: opensuse
author: Ale gargolario
image: /images/opensuse-logo.png
tags:
 - opensuse
 - bash
 - zypper
 - repos
---

Muchas veces añadimos un repositorio de terceros a nuestro querido **openSuSE** para instalar tal o cual
programa. Pues bien, una vez añadido el repo, podemos llevar a cabo una serie de acciones para modificar su estado
a nuestro gusto. Esto se puede hacer vía **YaST** o vía consola con **zypper**. En esta ocasión, nos centraremos en
la segunda vía.

Tomaremos como ejemplo el repo **VLC**. Vamos a ello:

### Activación del repo

```bash
zypper mr -e VLC
```

### Desactivación del repo

```bash
zypper mr -d VLC 
```
### Actualización automática del repo

```bash
zypper mr -r VLC
```
### Desactivación de la actualización automática del repo

```bash
zypper mr -R VLC
```

Halof!!!


[![_config.yml]({{ site.baseurl }}/images/opensuse-logo.png)](https://es.opensuse.org)

#### Notas:
+ **zypper** puede referirse a un repo por su nombre, alias o número indistintamente. Para ver una lista de todos los repositorios con toda esta información podemos utilizar la siguiente orden en consola:

```bash
zypper repos
```

#### Fuentes
*** 

**Web de opensuse:** <https://es.opensuse.org>
