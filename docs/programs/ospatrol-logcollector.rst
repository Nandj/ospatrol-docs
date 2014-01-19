
.. _ospatrol-logcollector:

ospatrol-logcollector
=============

The ``ospatrol-logcollector`` daemon monitors configured files and commands for new log messages.
``ospatrol-logcollector`` is configured in ospatrol.conf.  (see :ref:`ospatrol_config.localfile`)


ospatrol-logcollector argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-logcollector

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-logcollector`` in the foreground.

.. option:: -c <config>

    Run ``ospatrol-logcollector`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


