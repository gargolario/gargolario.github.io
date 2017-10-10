---
layout: post
title: Tipos de shell y clasificación de archivos de arranque de Bash
date: 2017-10-10
summary: Personalizando el entorno de Bash
categories: lpic1 
author: Ale-gargolario
image: /images/bash.png
tags:
 - lpic1
 - bash
 - scripts-de-arranque
---

Lo primero que hace **Bash** cuando lo iniciamos es leer los **archivos** o **scripts de arranque** — los cuales sirven para personalizar el entorno de las sesiones, bien a nivel **global**, bien a nivel de **usuario**.

Ahora bien, el tipo de archivo de arranque que se lee viene determinado por un parámetro fundamental: **el tipo de shell o terminal**. Veamos qué tipos de shell existen:

## <span style="color:green">**Tipos de shell**</span>

### Shell interactiva de login

Es aquella en la que el usuario introduce las órdenes en la terminal a través del teclado (**interactiva**) y representa la vía por la que el usuario ingresa o se *loguea* en el sistema (**de login**).

#### Ejemplos

+ Terminales **SSH**

+ Accesos a una sesión Bash con `su - username`

+ Desde una interfaz gráfica, terminales abiertas con la combinación de teclas **ctrl \+ alt \+ teclas de función** (desde **F1-F6**) — con la combinación **ctrl \+ alt \+F7** se restablece la interfaz gráfica. 

### Shell interactiva de no-login

Es aquella en la que el usuario introduce las órdenes en la terminal a través del teclado (**interactiva**) y es, en realidad, un emulador de terminal que se inicia desde un entorno gráfico después del ingreso o *logueo* del usuario en el sistema (**de no-login**).

#### Ejemplos

+ **gnome-terminal**, **konsole**, etc.


### Shell no interactiva y de no-login

Es aquella en la que no hay interacción con el usuario (**no interactiva**) ni *logueo* alguno (**de no-login**). Se trata, básicamente, del uso de **scripts**. En estos casos, Bash no lee ninguno de los archivos de arranque. 

#### Ejemplos

+ **Scripts** para realizar tareas **cron**, etc.





