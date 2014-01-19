
.. _ospatrol-syscheckd:

ospatrol-syscheckd
=============

The ``ospatrol-syscheckd`` daemon checks configured files for changes to the checksums, permissions or ownership.
``ospatrol-syscheckd`` is started by ospatrol-control.
Configuration for ospatrol-syscheckd is handled in the ospatrol.conf. 

See :ref:`manual-syscheck` for more detailed configuration information.

ospatrol-syscheckd argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-syscheckd

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-syscheckd`` in the foreground.

.. option:: -c <config>

    Run ``ospatrol-syscheckd`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


