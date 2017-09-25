---
layout: post
title:  Grep only uncommented lines
date:	2017-9-23
categories:	LPIC-1
---

In our daily work as sysadmins we sometimes bump into very large config files when we are only interested in a line or two.
In this scenario our old good friend **grep** comes in handy.

## Get rid of all lines containing **#**
***
We use the **-v** parameter to invert the search

```bash
grep -v '#' config_file
```

## Get rid of all lines starting with **#**
***
We use **^** to indicate start of line

```bash
grep -v '^#' config_file
```


Halof!!!

[![_config.yml]({{ site.baseurl }}/images/logo@2x.png)](https://www.lpi.org)
