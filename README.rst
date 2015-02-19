
How to deploy a PRAGMA perfsonar node
=====================================

This guide will help you to install a Perfsonar node to join the
PRAGMA Perfsonar MESH.

Installing you Perfsonar node
-----------------------------

To install your Perfsonar node download the 6.2 kernel roll
from the `Rocks web site <http://www.rocksclusters.org/>`_
in the download section.

At the moment to access Rocks 6.2 you need to our `beta web
site <http://beta6.rocksclusters.org/isos/>`_, when Rocks 6.2
will be release it will be available from the main web site.

Burn the ISO on a CD and install your server booting from that
CD. At boot time make sure to type `build` and **to add all the 
networking parameters** as indicated on the screen (if you don't
do that you will not be able to fetch the required Rolls in the
next screen).

At the next screen type `beta6.rocksclusters.org` as `Hostname of 
Roll Server` and click on Download. Then select the following Rolls:

- kernel
- base
- os
- perfSONAR
- web-server

Follow the standard installation procedure (as indicated in the
`users guide 
<http://central6.rocksclusters.org/roll-documentation/base/6.1.1/install-frontend.html>`_),
make sure to enter the proper networking information or you will
have to repeat the installation process.

When you get to the `Install perfSONAR WebUI Frontend` select
`Install WebUI on Frontend`. You can select `Auto Partitioning`
unless you have some special needs.

Once the machine finishes the installation and reboot login and
select a username and a password for the web admin interface.






