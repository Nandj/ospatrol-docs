
.. _ospatrol-makelists:

ospatrol-makelists
=============

The ``ospatrol-makelists`` utility to compile cdb databases.
``ospatrol-makelists`` will scan ospatrol.conf for database files, check the mtime, and recompile all out of date databases.

See :ref:`manual-rule-lists` for more information.

ospatrol-makelists argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-makelists 

.. option:: -h

    Display the help message. 

.. option:: -V

    Diplay the version and license information.

.. option:: -d

    Execute in debug mode.

.. option:: -f

    Force rebuild of all databases.

.. option:: -u <user>

    Run as <user>.

.. option:: -g <group>

    Run as <group>.

.. option:: -c <config>

    Run with configuration file of <config>.

    **Default** /var/ospatrol/etc/ospatrol.conf

.. option:: -D <dir>

    Chroot to <dir>.

    **Default** /var/ospatrol



ospatrol-makelists example usage
~~~~~~~~~~~~~~~~~~~~~~~~~~~



Example: Running ospatrol-makelists and an update is necessary
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

    # /var/ospatrol/bin/ospatrol-makelists
     * File lists/blocked.txt.cdb need to be updated


Example: Running ospatrol-makelists when no update is necessary
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console 

    # /var/ospatrol/bin/ospatrol-makelists
     * File lists/blocked.txt.cdb does not need to be compiled

