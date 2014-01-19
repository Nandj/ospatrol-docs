
.. _ospatrol-csyslogd:

ospatrol-csyslogd
=============

``ospatrol-csyslogd`` is a daemon that forwards the OSPatrol alerts via syslog.
Configuration is done in the ``<syslog_output>`` section of the ospatrol.conf. (see :ref:`ospatrol_config.syslog_output`)


ospatrol-csyslogd argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-csyslogd

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-csyslogd`` in the foreground.

.. option:: -u <user>

    Run ``ospatrol-csyslogd`` as <user>.

    **Default:** ospatrolm

.. option:: -g <group>

    Run ``ospatrol-csyslogd`` as <group>.

.. option:: -c <config>

    Run ``ospatrol-csyslogd`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


