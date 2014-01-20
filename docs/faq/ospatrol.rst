.. _faq_ospatrol:

OSPatrol: FAQ
-------------

.. contents:: 
    :local:


Can an OSPatrol manager have more than 256 agents?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  By default OSPatrol limits the number of agents to 256 per manager. This limitation is set in the code, but can be modified at compile time.
  Depending on the event load, a manager running on modern hardware can handle many more agents.
  Some users have more than 1000 agents on a single manager.
  To change the maximum number of agents, cd into the src directory and run the following command:

  .. code-block:: console

      make setmaxagents


  You should be prompted for the number of agents to allow.

  One issue you may face after changing this setting is the number of files allowed to be open for a single user.
  The users ``ospatrol`` and ``ospatrolr`` both open at least 1 file (syscheck database and rids file) per agent.
  Raising this limit is operating system specific.

  Some Linux distributions support a ``/etc/security/limits.conf``. Set the limits to be at least a few files above what the max agents is set to.

  .. code-block:: console

     ospatrol            soft    nofile          2048
     ospatrol            hard    nofile          2048
     ospatrolr           soft    nofile          2048
     ospatrolr           hard    nofile          2048



Where are OSPatrol's logs stored?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  On OSPatrol server and local installs there are several classes of OSPatrol logs. 
  There are the logs created by the OSPatrol daemons, the log messages from the agents, and the alerts.
  Agent installs do not have logs from other agents or alerts, but do have logs created by the OSPatrol processes.

  All logs are stored in subdirectories of ``/var/ospatrol/logs``. 
  OSPatrol's log messages are stored in ``/var/ospatrol/logs/ospatrol.log``.

  Log messages from the agents are not stored by default. After analysis they are deleted unless the <logall> option is included in the manager's ospatrol.conf. 
  If set all log messages sent to the manager are stored in ``/var/ospatrol/logs/archives/archives.log`` and rotated daily.

  Alerts are stored in ``/var/ospatrol/logs/alerts/alerts.log``, and rotated daily.


Where can I view the logs sent to an OSPatrol manager (or on a local install)?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  OSPatrol does not store the logs sent to it by default. If a log does not trigger an alert it is discarded, and logs that do trigger alerts are stored with the alerts in ``/var/ospatrol/logs/alerts``.

  The ``<log-all>`` option can be added to the ``<global>`` section (see: :ref:`ospatrol_config.global`) of the manager's ospatrol.conf. The manager's OSPatrol processes should be restarted.
  The raw logs will then be saved to files, organized by date, in ``/var/ospatrol/logs/archives``.

  The headers attached to these log messages are in the format of ``"YYYY Month dd HH:MM:ss agent_name->/path/to/log/file "``.

  .. code-block:: console

      2011 Aug 04 00:00:01 server->/var/log/local7 Aug  4 00:00:26 server named[29909]: client 192.168.1.7#39323: query: fake.example.net IN AAAA +


Can OSPatrol's logs be saved to a different directory?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  As a protection mechanism, OSPatrol chroots most of its processes to the install directory (typically ``/var/ospatrol``). 
  Due to this chroot, logs must be saved to a location under ``/var/ospatrol``.
  OSPatrol does rotate its logs, but will not be able to move them from ``/var/ospatrol``.

  Be sure to allocate enough space to ``/var/ospatrol``.



I'm getting an error when starting OSPatrol: "OSPatrol analysisd: Testing rules failed. Configuration error. Exiting." Why?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  There was a small bug in the ospatrol-control script that was not caught in time for 2.6.
  The error comes from the script trying to run ospatrol-logtest from the wrong directory.
  The solution is to change the line where ospatrol-logtest is running to look like this:

  .. code-block:: console

      echo | ${DIR}/bin/ospatrol-logtest > /dev/null 2>&1;


The rules aren't on my agents, they're only on the server!
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  That's not a question. Also, that's the way it is. Only the server has the rules. Agents do not get a copy of the rules.


Do the rules get pushed to the agents automatically?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  The rules only exist on the manager. All analysis is done on the manager.
  Agents do not send alerts to the manager, they only send the raw logs.


How can I get ospatrol.log to rotate daily?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

  Currently OSPatrol does not rotate the ``ospatrol.log``, use logrotate.d or newsyslog to rotate it for now.

