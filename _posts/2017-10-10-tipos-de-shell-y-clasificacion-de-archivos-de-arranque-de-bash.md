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

Bien, pues ya lo tenemos todo listo para crear una tabla resumen donde podamos consultar de forma clara qué archivo se lee en qué situación:

## <span style="color:green">**Tabla resumen comparativa de archivos de arranque de Bash**</span>


|                   ||||||||||||||       | **Login files**         |       |       ||||||||||||||||||||||| **Non-login files**  |
|-------------------||||||||||||||---|---|:------------------------|-------|---|---|||||||||||||||||||||||:---------------------|
|                   ||||||||||||||       |                         |       |       |||||||||||||||||||||||                      |
|**Global files**   ||||||||||||||       |*/etc/profile*           |       |       |||||||||||||||||||||||*/etc/bash.bashrc*    |
|                   ||||||||||||||       |*/etc/profile.d/\**      |       |       |||||||||||||||||||||||*/etc/bash/bashrc*    |
|                   ||||||||||||||       |                         |       |       |||||||||||||||||||||||*/etc/bashrc*         |
|                   ||||||||||||||       |                         |       |       |||||||||||||||||||||||                      |
|**User files**     ||||||||||||||       |*~/.bash_profile*        |       |       |||||||||||||||||||||||*~/.bashrc*           |
|                   ||||||||||||||       |*~/.bash_login*          |       |       |||||||||||||||||||||||                      |
|                   ||||||||||||||       |*~/.profile*                     |       |||||||||||||||||||||||                      |

## <span style="color:green">**¿Cómo sé qué tipo de shell tengo?**</span>

Si tienes abierta una Bash shell y no sabes de qué tipo se trata, puedes averiguarlo así:





