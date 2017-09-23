---
layout: post
title: LPIC1 - Grep only uncommented lines
---

In our daily work as sysadmins we sometimes bump into very large config files when we are only interested in a line or two.
In this scenario our old good friend ++grep ++ comes in handy.

## Get rid of all lines containing the pound symbol (**#**)
***
We use the ++-v++ parameter to invert the search

```bash
grep -v '#' config_file
```

## Get rid of all lines starting with ++#++
***

```bash
grep -v '^#' config_file
```


Halof!!!

[![_config.yml]({{ site.baseurl }}/images/logo@2x.png)](https://www.lpi.org)
