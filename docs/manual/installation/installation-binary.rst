.. _manual-install-binary:

Binary Installation 
===================

On some systems a compatible compiler is not available, this leads to problems for the
standard OSPatrol install method. To work around this OSPatrol supports being built on one
system and installed on another.

.. note:: 

    Due to the way OSPatrol is built the system compiling OSPatrol must be the same OS and
    CPU platform for this work correctly. 

.. _manual-install-binary-build: 

Compiling OSPatrol for install on a second server 
----------------------------------------------

First download the OSPatrol package corresponding to the version you want to 
install and unpack it (on the system with a compiler).

.. code-block:: console 

    # wget http://www.ospatrol.net/files/ospatrol-hids-latest.tar.gz  
    # tar -zxvf ospatrol-hids-latest.tar.gz 
    # rm ospatrol-hids-latest.tar.gz 

    
Enter in the source directory of the downloaded package and compile OSPatrol. 

.. code-block:: console 

    # cd ospatrol-*/src
    # make setagent                
    # make all
    # make build
    # cd ../..

Modify ospatrol-hids-*/etc/preloaded-vars.conf to set BINARY_INSTALL to yes. 

.. code-block:: console 

    # echo "USER_BINARYINSTALL=\"y\"" >> ospatrol-hids*/etc/preloaded-vars.conf

Finally create an OSPatrol package.

.. code-block:: console 

    # tar -cvzf ospatrol-binary.tgz ospatrol-hids* 

.. _manual-install-binary-install: 

Installation of the binary OSPatrol package 
----------------------------------------

On the target system (that does not have a C compiler) download your ospatrol-binary.tgz 
created in the setups above. 

.. code-block:: console 

    # cd /tmp
    # scp root@builder-server.example.com:/tmp/ospatrol-binary.tgz . 

Complete the installation by unarchiving the binary package and running ./install.sh. 

.. code-block:: console 

    # tar xfvz ospatrol-binary.tgz 
    # cd ospatrol-* 
    # ./install.sh 

After following the installation prompts your install will be complete.  



