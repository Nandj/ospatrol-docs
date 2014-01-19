
.. _ospatrol-dbd:

ospatrol-dbd
=============

The ``ospatrol-dbd`` daemon inserts the alert logs into a database, either postgresql or mysql.
``ospatrol-dbd`` is configured in ospatrol.conf.  (see :ref:`ospatrol_config.database_output`)


ospatrol-dbd argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-dbd

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-dbd`` in the foreground.

.. option:: -u <user>

    Run ``ospatrol-dbd`` as <user>.

    **Default:** ospatrolm

.. option:: -g <group>

    Run ``ospatrol-dbd`` as <group>.

.. option:: -c <config>

    Run ``ospatrol-dbd`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


