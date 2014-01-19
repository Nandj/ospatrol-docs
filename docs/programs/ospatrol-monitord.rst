
.. _ospatrol-monitord:

ospatrol-monitord
=============

The ``ospatrol-monitord`` daemon monitors agent connectivity and compress daily log files.
``ospatrol-monitord`` is configured in ospatrol.conf.  (see :ref:`ospatrol_config.localfile`)


ospatrol-monitord argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-monitord

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-monitord`` in the foreground.

.. option:: -u <user>

    Run ``ospatrol-monitord`` as <user>.

    **Default:** ospatrolm

.. option:: -g <group>

    Run ``ospatrol-monitord`` as <group>.

.. option:: -c <config>

    Run ``ospatrol-monitord`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


