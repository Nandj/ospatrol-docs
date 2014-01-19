
.. _ospatrol-execd:

ospatrol-execd
=============

``ospatrol-execd`` executes active responses by running the configured scripts.
``ospatrol-execd`` is configured in the ospatrol.conf. (see :ref:`ospatrol_config.active-response`)

ospatrol-execd argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-execd

.. option:: -d

    Run in debug mode.

.. option:: -V

    Version and license information.

.. option:: -h

    Display the help message.

.. option:: -t

    Test configuration.

.. option:: -f

    Run ``ospatrol-execd`` in the foreground.

.. option:: -c <config>

    Run ``ospatrol-execd`` using <config> as the configuration file.

    **Default:** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default:** /var/ospatrol


