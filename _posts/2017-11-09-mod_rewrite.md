---
layout: post
title: Set Up mod_rewrite
subtitle: How To Set Up mod_rewrite for Apache
gh-repo: sherafatian/sherafatian.github.io
gh-badge:
  - star
  - fork
  - follow
published: true
date: '2017-11-09'
---

# How To Set Up mod_rewrite for Apache

## Step 1 — Installing Apache

In this step, we will use a built-in package installer called `apt-get`. It simplifies management drastically and facilitates a clean installation.

First, update the system's package index. This will ensure that old or outdated packages do not interfere with the installation.
```
sudo apt-get update
```
Apache2 is the aforementioned HTTP server and the world's most commonly used. To install it, run the following:
```
sudo apt-get install apache2
```
## Step 2 — Enabling mod_rewrite

Now, we need to activate `mod_rewrite`.
```
sudo a2enmod rewrite
```
This will activate the module or alert you that the module is already in effect. To put these changes into effect, restart Apache.
```
sudo service apache2 restart
```
## Step 3 — Setting Up .htaccess

In this section, we will setup a `.htaccess` file for simpler rewrite rule management.

A `.htaccess` file allows us to modify our rewrite rules without accessing server configuration files. For this reason, `.htaccess` is critical to your web application's security. The period that precedes the filename ensures that the file is hidden.

We will need to set up and secure a few more settings before we can begin.

First, allow changes in the `.htaccess` file. Open the default Apache configuration file using `nano` or your favorite text editor.
```
sudo nano /etc/apache2/sites-enabled/000-default.conf
```
Inside that file, you will find the `<VirtualHost *:80>` block on line 1. Inside of that block, add the following block:
```
/etc/apache2/sites-available/default
<Directory /var/www/html>
                Options Indexes FollowSymLinks MultiViews
                AllowOverride All
                Order allow,deny
                allow from all
</Directory>
```
Your file should now match the following. Make sure that all blocks are properly indented.
```
/etc/apache2/sites-available/default
<VirtualHost *:80>
    <Directory /var/www/html>

        . . .

    </Directory>

    . . .
</VirtualHost>
```
To put these changes into effect, restart Apache.
```
sudo service apache2 restart
```
