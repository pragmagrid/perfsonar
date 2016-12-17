
How to deploy a PRAGMA perfsonar node
=====================================

This guide will help you to install a Perfsonar node to join the
PRAGMA Perfsonar MESH.

Installing you Perfsonar node
-----------------------------
To install your Perfsonar node You will need to do the installation of the ZOTAC box 
and install the **perfSONAR** roll at the time of the building the node as a 
**ROCKS frontend**.  
Please follow the steps below.

#. **Download perfSONAR ISO** from `perfSONAR ISO`_

   Burn the ISO on a CD/DVD. 

#. **Download the 6.2 kernel roll** from the `Rocks Downloads`_.  

   Burn the ISO on a CD/DVD. 
   
#. **Build  your server using kernel CD**

   #. At boot time make sure to type *build* and *to add all the networking parameters* 
      using parameters as indicated on the screen. 
      Make sure to enter the proper networking information or you will
      have to repeat the installation process because 
      you will not be able to fetch the required Rolls in the next screen.

   #. Follow the standard installation procedure as indicated in the `Users Guide`_. 

   #. At the next screen use a default host name  for rolls server, click on 
      **Download**, then select the following rolls:: 

          - kernel
          - base
          - os
          - web-server

      Then select *adding a roll* from CD/DVD  and use your perfSONAR CD to add
      the roll.

   #. Follow the standard installation procedure as indicated in the
      `Users Guide`_.  Usually,  we suggest an auto partition, but perfSONAR
      need more space for the /var.  The zotac box has 120Gb disk.  Select 
      **Manual Partitioning** and Make  the following partitions:: 
      
          / 32Gb  
          /var 35-40Gb 
          /export (the rest of the disk)

   #. When you get to the screen *Install perfSONAR WebUI Frontend* select
      *Install WebUI on Frontend*. 
      
   Once the installation finishes the host will reboot and is ready for login.
   
#. **Select a username and a password for the web admin interface**

   Login as root on a server console and  when prompted select username and
   password that will be used for perfSONAR.

#. **Configure the mesh client**

   #.  Edit the file **/etc/perfsonar/meshconfig-agent.conf** and add the lines::

          <mesh>
            configuration_url  http://data.ctc.transpac.org/meshes/pragma-mesh.json
          </mesh>
          configure_archives 1

   #. As tas the perfsonar user run a command::

          /usr/lib/perfsonar/bin/generate_configuration

#. When done, please advise about your perfSONAR box FQDN and the IP address.
   These will be added to the  pragma perfsonar mesh. And we will send you an IP
   address so that it can be added to the firewall at transpac

The maddash instance is located at `PRAGMA MESH`_


.. _perfSONAR ISO: https://drive.google.com/open?id=0B2VTJMbHpU8yNkdJT3NzLThPTlU
.. _Rocks Downloads: http://rocksclusters.github.io/downloads/2015-05-11-download-rocks-6-2-sidewinder.html
.. _Users Guide: http://rocksclusters.github.io/docs/guides.html
.. _PRAGMA MESH: http://data.ctc.transpac.org/maddash-webui/index.cgi?dashboard=PRAGMA%20Mesh
