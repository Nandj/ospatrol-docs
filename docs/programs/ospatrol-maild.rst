
.. _ospatrol-maild:

ospatrol-maild
=============

The ``ospatrol-maild`` daemon sends OSPatrol alerts via email.
``ospatrol-maild`` is started by ospatrol-control.
Configuration for ospatrol-maild is handled in the ospatrol.conf. (see :ref:`ospatrol_config.global`)

ospatrol-maild argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-maild

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-maild`` in the foreground.

.. option:: -u <user>

    Run ``ospatrol-maild`` as <user>.

    **Default:** ospatrolm

.. option:: -g <group>

    Run ``ospatrol-maild`` as <group>.

.. option:: -c <config>

    Run ``ospatrol-maild`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


