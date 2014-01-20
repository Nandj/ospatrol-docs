.. _ospatrol_101_install_server:



OSPatrol 101: Server Installation
------------------------------

Things to keep in mind:
^^^^^^^^^^^^^^^^^^^^^^^

Many of the OSPatrol daemons chroot to the installation directory (``/var/ospatrol`` is the default, and is the reference directory for this document).
All logs are currently kept in the ``/var/ospatrol/logs`` directory. Some log files are rotated daily, but OSPatrol does not move logs outside of ``/var/ospatrol/logs``.
Depending on a number of factors these logs can become large, so make sure you have enough space to store the logs you want to keep.

Related to the amount of storage space you give to OSPatrol is the "events per second" (EPS) you expect to receive. 
Michael Starks has provided a script to determine EPS in a blog post: `3WoO Day 2: Calculating Your EPS <http://www.immutablesecurity.com/index.php/2011/10/24/3woo-day-2-calculating-your-eps/>`_.
There has not been any formal load testing on OSPatrol, but some informal testing has shown a local installation can handle 11,000 EPS. (`email <http://osdir.com/ml/ospatrol-list/2010-09/msg00217.html>`_ by Christopher Moraes)
This test was done under mostly ideal conditions, but we would be interested in hearing performance reports from other users.

The number of rules and agents can also affect the speed of the OSPatrol manager, and the amount of space necessary for to hold the logs. More agents means more logs.
 
Installation process:
^^^^^^^^^^^^^^^^^^^^^

* Download the OSPatrol tarball and pgp/gnupg signature from `ospatrol.net <http://www.ospatrol.net/main/downloads>`_.

.. image:: images/install/download.png
   :align: center
   :alt: OSPatrol download

* Use GnuPG or PGP to verify the download. Use ``gpg --import OSPatrol-GPG-Key.asc`` to import the OSPatrol gpg key, then ``gpg --verify ospatrol-hids-2.6.tar.gz.sig ospatrol-hids-2.6.tar.gz`` to verify the signature and file.

.. image:: images/install/gpg-verify.png
   :align: center
   :alt: gpg --verify ospatrol-hids-2.6.tar.gz

* Unpack the tarball and change into the new directory with ``tar -zxf ospatrol-hids-2.6.tar.gz``. Run the install.sh script to perform the installation ``./install.sh``:

.. image:: images/install/install_sh.png
   :align: center
   :alt: cd ospatrol-hids-2.6 && ./install.sh

.. XXX IMAGE IS MISSING

* If you wish to output alert information to a database (MySQL or PostgreSQL) or to Prelude, run the appropriate ``make`` command in the ``src`` directory. For database output run ``make setdb`` and for Prelude use ``make setprelude``:

.. image:: images/install/install_set.png
   :alias: center
   :alt: cd ospatrol-hids-2.6/src && make setdb ; make setprelude 

* Verify the information and press ``ENTER``. ``System`` should detail the operating system and platform, ``User`` should be the current user, and ``Host`` should display the hostname.

.. image:: images/install/install_info.png
   :align: center
   :alt:  OSPatrol installation information

* The installation type for this install will be server, and we are using the default install directory. It should be possible to install OSPatrol anywhere in the system but selecting the default will be easiest. Items inside the brackets are the default answers.

.. image:: images/install/install_questions.png
   :align: center
   :alt: OSPatrol installation questions

* This installation will be configured to send email, integrity check daemon, and the rootkit detection engine.

.. image:: images/install/more_questions.png
   :align: center
   :alt: OSPatrol more installation questions

* We will be disabling active response for now. Active response deserves its own section, and will be covered later.

.. image:: images/install/active-response.png
   :align: center
   :alt: OSPatrol disable active response

* We will also disable remote syslog (using OSPatrol's syslog will be covered later). The script prints a log file that will be analyzed in addition to the typical log files. In this case it is a Debian specific log file.

.. image:: images/install/disable-syslog.png
   :align: center
   :alt: OSPatrol disable syslog

* At this point OSPatrol will be compiled. After compilation has completed, the script provides more information:

.. image:: images/install/post-installation.png
   :align: center
   :alt: OSPatrol post installation message





Adding an agent:
^^^^^^^^^^^^^^^

* Adding agents is done with the manage_agents application:

.. image:: images/install/manage_agents_intro.png
   :align: center
   :alt: cd /var/ospatrol/bin && ./manage_agents

* The manage_agents menu is simple, enter ``a`` to add an agent:

.. image:: images/install/manage_agents_add.png
   :align: center
   :alt: Add an agent with a

* Enter the agent's information. In the IP address field a CIDR (192.168.1.0/24) or ``any`` can be used:

.. image:: images/install/manage_agents_add2.png
   :align: center
   :alt: OSPatrol manage_agents agent information

* After confirming the addition, manage agents will notify you that the OSPatrol processes must be restarted:

.. image:: images/install/manage_agents_add3.png
   :align: center
   :alt: OSPatrol manage_agents exit

.. note::

   Restarting the OSPatrol processes is only necessary for the initial agent.
   While subsequent additions will still give the message, the restart is not necessary.

* Restarting the OSPatrol processes:

.. image:: images/install/manage_agents_restart.png
   :align: center
   :alt: cd /var/ospatrol/bin && ./ospatrol-control restart



