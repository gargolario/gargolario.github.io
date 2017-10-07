---
layout: post
title: Switch package vendor with zypper
date: 2017-9-30
summary: Updating packages to version in a different repo
categories: opensuse 
author: Ale gargolario
image: /images/terminal-suse.png
tags:
 - opensuse
 - zypper
 - bash
---

Everyone who has ever used **openSUSE** is bound to know what **YaST** is. That's right: *Yet another Setup Tool* ... and a lot more!!!
Actually, **YaST** allows you to switch package vendor (eg: you have **mplayer** - and a whole lot of other programmes for that matter -
installed in your system from repo **x**, but you wanna have the version from repo **y**).

In this post we are gonna learn how to do that in the terminal with **zypper**.

### Switching all current packages to the versions in repo y

```bash
zypper dup --from y
```

That's it! All packages which have a version in repo **y** will be installed in your system.


Halof!!!


![_config.yml]({{ site.baseurl }}/images/terminal-suse.png)

#### Notes:
+ When specifying a repo to **zypper**, you can use either its **name**, **url** or **number**. To get these values,
you can type **zypper repos** into the terminal.

#### Sources
***

**openSUSE Website:** <https://en.opensuse.org/>
