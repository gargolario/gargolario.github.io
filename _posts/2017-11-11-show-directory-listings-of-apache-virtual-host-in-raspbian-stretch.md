---
layout: post
title: Show directory listings of apache virtual host in Raspbian stretch
date: 2017-11-11
summary: Showing directory contents with mod_autoindex.c
categories: lpic2
author: Ale gargolario
image: /images/web-server.png
tags:
 - lpic2
 - raspbian
 - apache
 - directory-listing
---

Ok, so we have installed **apache**. Now we want to set up a basic web server on our **Raspberrypi** and be able
to navigate through the contents of its directories. Let's get the task divided into 4 simple steps and down to work:

### Step 1: enable mod_autoindex

This module will take care of the job:

``` bash
sudo a2enmod autoindex
```
Once enabled, we can check (and tweak) its configuration in **/etc/apache2/mods-enabled/autoindex.conf**:

Let's move on to the next step.

### Step 2: Create your virtual host 

Go to **/etc/apache2/sites-available/** and either use the default virtual host configuration file or copy it to a new file like so:


``` bash
cp 000-default.conf my-virtual-host.conf
```
Now modify the config file to meet your needs:


``` bash
<VirtualHost *:80>
    ServerAdmin webmaster@localhost
    DocumentRoot /var/www/html/my-virtual-host
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

```
Don't forget to enable the newly created virtual host with:

``` bash
sudo a2ensite my-virtual-host
```

On to the next step.

### Step 3: Make sure the icons directory is where it should be

Make sure the **icons** directory is in the directory indicated by the **DocumentRoot** directive:

``` bash
ls /var/www/html/my-virtual-host
```
Again, make sure you see the **icons** directory in the output of the above command.

Last, but not least ...


### Step 4: Enable *Options +Indexes* 

To start with, make sure no **index.html** file (or a similar one like **index.htm** or **index.php**) exits in our virtual host's **DocumentRoot**:

``` bash
ls /var/www/html/my-virtual-host
```
If an *index* file exists, change its name to avoid having it shown by default when accessing the web server.

Finally, activate the option **+Indexes** either:

In **apache**'s main config file **/etc/apache2/apache2.conf**:

``` bash
<Directory /var/www/html/my-virtual-host>
  Options +Indexes
</Directory>
```

or in **/var/www/html/my-virtual-host/.htaccess**:

``` bash
Options +Indexes
```

Now you're ready to restart **apache** and have it show directory listings.

Halof!!!

![_config.yml]({{ site.baseurl }}/images/web-server.png)

#### Recursos de interés
*** 

 Wiki de apache: <https://wiki.apache.org/httpd/DirectoryListings>

