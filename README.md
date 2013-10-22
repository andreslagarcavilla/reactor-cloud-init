README
======

This repo contains a cloud-init script for easy reactor installation.

Requirements
------------

Currently this script supports automated reactor installation on Ubuntu 12.04
(LTS) and CentOS 6.x.

Usage
-----

To use it, simply edit the `cloud-init` file for your distro and change ${KEY}
to your repository key.

(You could also use `sed` or other such trickery to make the change.)

Then, pass the cloud-init file as user data when you boot your instance, for example:

    nova boot --user-data=cloud-init --flavor=1 reactor

CentOS Note
-----------

Cloud-init is provided by the EPEL package repository. You also need to enable
EPEL to obtain some of reactor's dependencies. You can enable EPEL and install
cloud-init as follows:

    rpm -ivh http://dl.fedoraproject.org/pub/epel/6/`uname -m`/epel-release-6-8.noarch.rpm
    rpm --import https://fedoraproject.org/static/0608B895.txt
    yum -y install cloud-init
