README
======

This repo contains a cloud-init script for easy reactor installation.

Requirements
------------

Currently this script supports automated reactor installation on Ubuntu 12.04 (LTS).

Usage
-----

To use it, simply pass the cloud-init file as user data when you boot your
instance, for example:

    nova boot --user-data=cloud-init --flavor=1 reactor
