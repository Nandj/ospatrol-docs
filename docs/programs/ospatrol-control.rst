
.. _ospatrol-control:

ospatrol-control
=============

``ospatrol-control`` is a script to start, stop, configure, or check on the status of OSPatrol processes.
``ossc-control`` can enable or disable client-syslog, database logging, agentless configurations, and debug mode.

ospatrol-control argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


    .. _ospatrol-control-start::
    **start**
      Start the OSPatrol processes.

    .. _ospatrol-control-stop::
    **stop**
      Stop the OSPatrol processes.

    .. _ospatrol-control-restart::
    **restart**
      Restart the OSPatrol processes.

    .. _ospatrol-control-reload::

    **reload**
      Restart all OSPatrol processes except ``ospatrol-execd``. This allows an agent to reload without losing active response status.

      .. note::

         This is only available on an OSPatrol agent.

    .. _ospatrol-control-status::
    **status**
      Determine which OSPatrol processes are running.

    .. _ospatrol-control-enable::
    **enable**
      Enable OSPatrol functionality.

        .. _ospatrol-control-enable-database::
        **database**
          Enable the ``ospatrol-dbd`` daemon for logging to a database.

          **Available:** Server and local installs only.

          .. note::
              Database support must be compiled in at install time.

        .. _ospatrol-control-enable-client-syslog::
        **client-syslog**
          Enable ``ospatrol-csyslogd`` for logging to remote syslog.

          **Available:** Server and local installs only.

        .. _ospatrol-control-enable-agentless::
        **agentless**
          Enable ``ospatrol-agentlessd`` for running commands on systems without OSPatrol agents.

          **Available:** Server and local installs only.

        .. _ospatrol-control-enable-debug::
        **debug**
          Run all OSPatrol daemons in debug mode.


    .. _ospatrol-control-disable::
    **disable**
      Disable OSPatrol functionality.

        .. _ospatrol-control-disable-database::
        **database**
          Disable the ``ospatrol-dbd`` daemon for logging to a database.

          **Available:** Server and local installs only.

          .. note::
              Database support must be compiled in at install time.

        .. _ospatrol-control-disable-client-syslog::
        **client-syslog**
          Disable ``ospatrol-csyslogd`` for logging to remote syslog.

         **Available:** Server and local installs only.

        .. _ospatrol-control-disable-agentless::
        **agentless**
          Disable ``ospatrol-agentlessd`` for running commands on systems without OSPatrol agents.

          **Available:** Server and local installs only.

        .. _ospatrol-control-disable-debug::
        **debug**
          Turn off debug mode.



ospatrol-control example usage
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Example: Running ospatrol-control
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

    # /var/ospatrol/bin/ospatrol-control

    Usage: /var/ospatrol/bin/ospatrol-control {start|stop|restart|status|enable|disable}


