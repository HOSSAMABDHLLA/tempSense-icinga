=============
**tempSense**
=============

A simple Icinga2 plugin. The plugin allows the values of different sensors
to be read.

Usage
=======

* -id   - sensor ID
* -s    - sensor name (temp1, temp2 ...)
* -w    - warning threshold
* -c    - critical threshold

.. code-block:: console

    $ tempSense -id 4 -s temp1 -w 65 -c 80
    OK sensor Value: 61.75 | Tctl=61.75;65;80
    $
    $ tempSense -id 4 -s temp1 -w 65 -c 80 -l CPU_Temp
    OK sensor Value: 57.25 | CPU_Temp=57.25;65;80

..


*If unsure about the ID then the sensors can be probed as follows*
.. code-block:: console

    $ for i in \`seq 0 10\` ; do echo Probing [hwmon$i]; ./tempSense -id $i -s temp1 ; done

..


Installation
=============

* tempSense must be placed in your Icinga plugin directory

Configuration
==============

* Command definition - see command-plugins.conf
* Host configuration - see host_configuration.conf

