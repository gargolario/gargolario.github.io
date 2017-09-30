---
layout: post
title: Equivalencia de los modelos OSI y TCP
date: 2017-9-30
summary: Comparando modelos de comunicación por capas
categories: redes cisco 
author: Ale gargolario
image: /images/network.png
tags:
 - redes
 - cisco
 - osi
 - tcp
---


Tanto OSI como TCP estandarizan, en forma de abstracción por capas lógicas, las comunicaciones entre sistemas informáticos: cada capa recibe
información de la capa que tiene por debajo, y la pasa a la que tiene por encima.

En la siguiente tabla comparativa la parte inferior representa al nivel físico (interfaz de red, switches, ...); la parte superior, al usuario
(programas, procesos, ...).


### Tabla comparativa de los modelos OSI & TCP

| **OSI**							          |       |**TCP**						       |
| ----------------------------------------------------- 	          | :----: |:---------------------:				       |
| <span style="color:green">**Aplicación**</span> (programas de usuario)  |						         	       |
| <span style="color:green">**Presentación**</span> (formateo de datos)   |  |<span style="color:green">**Aplicación**</span> (Datos)          |
| <span style="color:green">**Sesión**</span> (llegada al host)  	  |               	  			    	       	       |
|                                    	     				  |                       				       	       |
| <span style="color:blue">**Transporte**</span> (segmentos)		  |  |<span style="color:blue">**Transporte**</span> (UDP, TCP)        |
|                                    					  |                       			   	       	       |
| <span style="color:brown">**Red**</span> (paquetes)                  	  |  |<span style="color:brown">**Internet**</span> (IP)	       |
| 		  		     					  |                       			      	       	       |
| <span style="color:red">**Enlace**</span> (tramas)		          |			     				       	       |
| <span style="color:red">**Físico**</span> (bits)       		  |  |<span style="color:red">**Físico**</span> (MAC)   	       | 



Halof!!!


![_config.yml]({{ site.baseurl }}/images/network.png)

## Notas:
+ **OSI** significa *Open Systems Interconnection*.
+ **TCP** significa *Transmission Control Protocol*.




