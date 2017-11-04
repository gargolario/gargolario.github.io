---
layout: post
title: Sincronizar repositorios github remoto y local
date: 2017-11-04
summary: Una mini-guía básica para la sincronización de repos
categories: programación
author: Ale gargolario
image: /images/github.jpg
tags:
 - git
 - github
---

Una de las cosas que más me gustan de **github** es que nos permite trabajar prácticamente en cualquier lugar, en remoto o en local.
En este mini-post veremos cómo hacerlo.

### Creación de directorio local y clonación de repositorio remoto a local

Ya hemos creado nuestro repositorio en <https://github.com/>. Ahora lo que vamos a hacer es clonarlo a nuestro ordenador. Para ello,
lo primero es crearnos un directorio para tal fin:

``` bash
mkdir ~/directorio_repositorio
```
Una vez creado el directorio, nos movemos a él:

``` bash
cd ~/directorio_repositorio
```
Y, ahora sí, clonamos nuestro repositorio de **github** desde Internet:

``` bash
git clone https://github.com/vuestro-usuario/vuestro-repositorio
```
Ahora ya podemos trabajar en nuestro repositorio de forma local.

### Sincronización de repositorio local a remoto

Cuando hayamos trabajado en local y queramos sincronizar con nuestro repositorio remoto en los servidores de **github**, 
haremos lo siguiente:

#### Comprobación de los cambios

``` bash
git status
```
Este comando nos informará de cuantos cambios hayamos añadido.

#### Añadido de los cambios

``` bash
git add *
```
Con este comando añadimos todos los cambios realizados a la lista de archivos para *comitear* al repositorio remoto (podemos
comprobar que han sido añadidos ejecutando de nuevo el comando **git status**). El siguiente paso es, por tanto, *comitear* 
esos archivos para poder sincronizarlos con el directorio remoto:

``` bash
git commit -m "nombre-del-comit"
```

#### Sincronizando con repositorio remoto

Finalmente, damos la orden para sincronizar nuestros cambios en local con el repositorio remoto:

``` bash
git push origin master
```

### Sincronización de repositorio remoto a local

A partir de ahora, cada vez que hagamos cambios en nuestro repositorio remoto, nos bastará con el siguiente comando para 
sincronizar en local:

``` bash
git pull
```
Por supuesto, no debemos olvidar que este comando ha de ejecutarse desde dentro del directorio del repositorio local que
creamos anteriormente (en nuestro caso **~/directorio_repositorio**).

Si volvemos a modificar en local y queremos sincronizar a remoto, volveremos a repetir los pasos explicados arriba:

``` bash
git add *
git commit -m "nombre-del-commit"
git push origin master
```

Halof!!!

![_config.yml]({{ site.baseurl }}/images/github.jpg)

#### Recursos de interés
*** 

 <https://www.atlassian.com/git/tutorials/syncing>

 <http://rogerdudler.github.io/git-guide/>
