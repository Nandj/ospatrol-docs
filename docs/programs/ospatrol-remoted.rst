
.. _ospatrol-remoted:

ospatrol-remoted
=============

``ospatrol-remoted`` is the server side daemon that communicates with the agents.
It can listen to port 1514/udp (for OSPatrol communications) and/or 514 (for syslog).
It runs as ospatrolr and is chrooted to ``/var/ospatrol`` by default.
``ospatrol-remoted`` is configured in the <remote> section of  ospatrol.conf. 
(see :ref:`ospatrol_config.remote`)


ospatrol-remoted argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-remoted

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -u <user>

    Run ``ospatrol-remoted`` as <user>.

    **Default:** ospatrolm

.. option:: -g <group>

    Run ``ospatrol-remoted`` as <group>.

.. option:: -c <config>

    Run ``ospatrol-remoted`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


