---
layout: post
title: Tipos de shell y clasificación de archivos de arranque de Bash
date: 2017-10-11
summary: Personalizando el entorno de trabajo de la terminal
categories: lpic1
author: Ale-gargolario
image: /images/bash.png
tags:
 - lpic1
 - bash
 - scripts-de-arranque
---

Lo primero que hace **Bash** cuando lo iniciamos es leer los **archivos** o **scripts de arranque** — los cuales sirven para personalizar el entorno de las sesiones, bien a nivel **global**, bien a nivel de **usuario**. Es en estos archivos donde podemos
escribir nuestros **aliases** preferidos, etc.

Ahora bien, el tipo de archivo de arranque que se lee viene determinado por un parámetro fundamental: **el tipo de shell o terminal**. 
Veamos qué tipos de shell existen: 

## <span style="color:green">**Tipos de shell**</span>

### Shell interactiva de login

Es aquella en la que el usuario introduce las órdenes en la terminal a través del teclado (**interactiva**) y representa la vía por la que el usuario ingresa o se *loguea* en el sistema (**de login**).

#### Ejemplos

+ Terminales **SSH**

+ Accesos a una sesión Bash con `su - username`

+ Desde una interfaz gráfica, terminales abiertas con la combinación de teclas **ctrl \+ alt \+ teclas de función** (**F1-F6**) — con la combinación **ctrl \+ alt \+F7** se restablece la interfaz gráfica. 

### Shell interactiva de no-login

Es aquella en la que el usuario introduce las órdenes en la terminal a través del teclado (**interactiva**) y es, en realidad, un emulador de terminal que se inicia desde un entorno gráfico después del ingreso o *logueo* del usuario en el sistema (**de no-login**).

#### Ejemplos

+ **gnome-terminal**, **konsole**, etc.


### Shell no interactiva y de no-login

Es aquella en la que no hay interacción con el usuario (**no interactiva**) ni *logueo* alguno (**de no-login**). Se trata, básicamente, del uso de **scripts**. En estos casos, Bash no lee ninguno de los archivos de arranque que se detallan más abajo. 

#### Ejemplos

+ **Scripts** para realizar tareas **cron**, etc.



Bien, pues ya lo tenemos todo listo para hacer un resumen donde podamos consultar de forma clara qué archivo se lee en qué situación (en los casos donde hay más de un archivo, Bash lee el primero que encuentra):

## <span style="color:green">**Resumen comparativo de archivos de arranque de Bash**</span>

### <span style="color:darkorange">**Archivos de arranque de shell interactiva de login**</span>

#### <span style="color:darkblue">**Nivel global**</span>

+ */etc/profile*
+ */etc/profile.d/\**

#### <span style="color:darkblue">**Nivel usuario**</span>

+ *~/.bash_profile*
+ *~/.bash_login* 
+ *~/.profile* 

### <span style="color:darkorange">**Archivos de arranque de shell interactiva de no-login**</span>

#### <span style="color:darkblue">**Nivel global**</span>

+ */etc/bash.bashrc*
+ */etc/bash/bashrc*
+ */etc/bashrc*

#### <span style="color:darkblue">**Nivel usuario**</span>

+ *~/.bashrc*

## <span style="color:green">**¿Cómo sé qué tipo de shell tengo?**</span>

Si tienes abierta una Bash shell y no sabes de qué tipo se trata, puedes averiguarlo así:

### Shell interactiva de login

Ejecutaremos el siguiente comando:

```bash
echo $0
```

Y nos dará como resultado:

```bash
-bash
```

o

```bash
-su
```


### Shell interactiva de no-login

Ejecutaremos el siguiente comando:

```bash
echo $0
```

Y nos dará como resultado:

```bash
bash
```
o

```bash
/bin/bash
```

Halof!!!

![_config.yml]({{ site.baseurl }}/images/bash.png)

#### Fuentes y recursos de interés:

**Manual de BASH en web de GNU:** <https://www.gnu.org/software/bash/manual/html_node/Bash-Startup-Files.html>
