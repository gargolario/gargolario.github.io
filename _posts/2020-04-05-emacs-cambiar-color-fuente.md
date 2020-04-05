---
layout: post
title: Cambiar color a fuente en EMACS
date: 2020-04-05
summary: Personaliza los colores de las fuentes de tus temas en emacs para trabajar a gusto
categories: emacs
author: Ale gargolario
image: /images/emacs.png
tags:
- emacs
- color
- fuentes
---

**GNU Emacs** es una maravilla de software multiplataforma; un entorno de trabajo **elisp** que te permite hacer prácticamente todo (programar, escuchar música, gestionar tu correo electrónico, surfear la web, etc.). 

Como sabrás, la personalización en **emacs** tampoco conoce límites y así lo demuestran la ingente cantidad de temas (y paquestes en general) disponibles que puedes encontrar -- por ejemplo -- en [MELPA](https://melpa.org/#/). Sin embargo, es posible que lleves utilizando **emacs** un tiempo y no sepas que puedes _tunearlo_ a tu gusto. A continuación te presento dos formas sencillas de modificar el color de las fuentes que a mí me han resultado de gran utilidad.


### Usar la posición del cursor

Mueve el cursor (o _punto_) a una parte del texto al que quieras cambiar el color. Una vez ahí, utiliza la combinación de teclas <kbd>CTRL</kbd>-<kbd>u</kbd>+<kbd>CTRL</kbd>-<kbd>x</kbd>+<kbd>=</kbd> que ejecutará la función `what-cursor-position` con el argumento _detalle_. Ya puedes moverte al nuevo búfer y navegar por él para realizar los cambios.


### Mostrar la lista completa de fuentes 

Con esta segunda opción puedes ver la lista de todas las fuentes (o _faces_ en la jerga de **emacs**) y -- a partir de ahí -- editarlas. Para ello, utiliza lo siguiente: <kbd>M</kbd> `list-faces-display` <kbd>RET</kbd>.


Espero que te sirvan estos pequeños consejos.


Halof!

![_config.yml]({{ site.baseurl }}/images/emacs.png)

#### Notas y enlaces de interés

+ Al momento de escribir este artículo, utilizo la versión **25.2.2** de **emacs**.

+ [Emacs Theme Gallery](https://pawelbx.github.io/emacs-theme-gallery/)

+ [GNU Emacs Custom Themes](https://www.gnu.org/software/emacs/manual/html_node/emacs/Custom-Themes.html)





