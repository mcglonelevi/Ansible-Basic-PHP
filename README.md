# Ansible Basic PHP

## Introduction

This is a simple starting point for provisioning a simple PHP webserver in a
simple and secure manner.  Most of the roles included in this script are
courtesy of geerlingguy (https://github.com/geerlingguy).  Most of geerlingguy's
roles are targeted at RHEL/CentOS and Debian/Ubuntu.  I have only tested this
on Ubuntu.

I have included a basic vagrant environemnt.

## Cloning and Basic Use

Clone this repo, then run `git submodule update --init`.  That will pull in the
various submodules required.

I have included a basic vagrant box for use in local testing.  If you need to
deploy to a remote server, add in a hosts file to suit your needs.

You will need to generate a self-signed cert if you plan to launch nginx using
SSL.  You will need to change the configuration accordingly.

You will also need to adjust the vagrant configuration (ports and synced folders)
if you want to test locally.

## What is included?

Basically, this installs MySQL, PHP 7.0 FPM, Certbot, Memcached, and Nginx.  If
you need more specific and/or different packages included, fork this and modify
it to your needs.

## Documentation

Basically, most of the documentation for the various submodules can be found here:

https://github.com/geerlingguy/ansible-role-certbot
https://github.com/geerlingguy/ansible-role-nginx
https://github.com/geerlingguy/ansible-role-mysql
https://github.com/geerlingguy/ansible-role-php

The only real custom part of this is the custom php.ini file.  Geerlingguy's
php.ini template was not as full-featured as I thought was necessary to setup
a secure PHP environment.  You can adjust the custom php.ini file in
`provisioning/roles/custom-php-ini/templates/php.ini.j2`  I have set up some
sensible defaults.  You may need to edit some settings to suit your 
needs.  If you see something that could use improvement, make a pull request
and I'll certainly take a look.
