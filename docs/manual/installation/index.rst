

.. _install:

Installation 
============

The best installation tutorial is available in the `OSPatrol book`_. 

.. _OSPatrol book: http://www.amazon.com/OSPatrol-Host-Based-Intrusion-Detection-Guide/dp/159749240X

__ OSPatrol Book install_


OSPatrol HIDS Manager/Agent Installation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Installation of the OSPatrol HIDS is very simple. Just follow these few steps to have 
it working.  Please make sure that you understand the type of installation you are choosing 
(manager, agent, local, or hybrid) and are also aware of the order (always install the manager 
first). If you don’t know what I’m talking about, it’s a good idea to visit the `install types
page`.

.. warning::

    Remember that when following this installation the commands only start after the # Everything 
    before that is just the information about the prompt

.. note::
   
    If you have experience with Unix, just download the latest version, uncompress it and run the 
    "./install.sh" script.

#. Download the latest version and verify its checksum.

    .. note:: 

        On some systems, the command md5, sha1 or wget may not exist, so try md5sum, sha1sum 
        or lynx respectively instead.

    .. code-block:: console

        # wget http://www.ospatrol.net/files/ospatrol-hids-2.6.tar.gz
        # wget http://www.ospatrol.net/files/ospatrol-hids-2.6_checksum.txt
        # cat ospatrol-hids-2.6_checksum.txt
        MD5 (ospatrol-hids-2.6.tar.gz) = f4140ecf25724b8e6bdcaceaf735138a
        SHA1 (ospatrol-hids-2.6.tar.gz) = 258b9a24936e6b61e0478b638e8a3bfd3882d91e
        MD5 (ospatrol-agent-win32-2.6.exe) = 7d2392459aeab7490f28a10bba07d8b5
        SHA1 (ospatrol-agent-win32-2.6.exe) = fdb5225ac0ef631d10e5110c1c1a8aa473e62ab4
        # md5sum ospatrol-hids-2.6.tar.gz 
        MD5 (ospatrol-hids-2.6.tar.gz) = f4140ecf25724b8e6bdcaceaf735138a
        # sha1sum ospatrol-hids-2.6.tar.gz
        SHA1 (ospatrol-hids-2.6.tar.gz) = 258b9a24936e6b61e0478b638e8a3bfd3882d91e


#. Extract the compressed package and run the “./install.sh” script (It will guide you 
   through the installation).

    .. code-block:: console 

        # tar -zxvf ospatrol-hids-*.tar.gz (or gunzip -d; tar -xvf)
        # cd ospatrol-hids-* 
        # ./install.sh

#. Remember to open port 1514 (UDP) if there is a firewall between the server and 
   the agents (not applicable to the local installation type).

#. If you are installing the server or the agent, remember to follow the `Managing 
   the agents section`.

#. Start OSPatrol HIDS 

    .. code-block:: console 

        # /var/ospatrol/bin/ospatrol-control start  

.. OSPatrol HIDS Windows agent Installation
.. ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. Windows agent installation has its own page at: :ref:`manual-win-install`. 

OSPatrol HIDS agentless Installation
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Agentless installation has its own page at: :ref:`manual-agentless`.

OSPatrol HIDS Binary installation 
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ 

On systems that do not have a C compiler or one is not allowed by policy 
installation can be done using :ref:`manual-install-binary`

OSPatrol Updates
~~~~~~~~~~~~~

Updating OSPatrol is as easy as it can get. Just download the latest package and follow 
the installation instructions as usual. It will detect that you already have it 
installed and ask:

.. code-block:: console
 
    - You already have OSPatrol installed. Do you want to update it? (y/n): y
    - Do you want to update the rules? (y/n): y

Just say “yes” to these questions and it will update everything properly. Your local rules 
and configuration options will not be modified. The same applies to the Unix or Windows 
agent updates.

External installation documents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


