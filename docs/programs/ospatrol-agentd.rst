
.. _ospatrol-agentd:

ospatrol-agentd
=============

``ospatrol-agentd`` is the client side daemon that communicates with the server.
It runs as ospatrol and is chrooted to ``/var/ospatrol`` by default.


ospatrol-agentd argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-agentd

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-agentd`` in the foreground.

.. option:: -u <user>

    Run ``ospatrol-agentd`` as <user>.

    **Default:** ospatrolm

.. option:: -g <group>

    Run ``ospatrol-agentd`` as <group>.

.. option:: -c <config>

    Run ``ospatrol-agentd`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


