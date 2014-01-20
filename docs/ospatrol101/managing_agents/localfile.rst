
Monitoring a log file:
----------------------

Configuring OSPatrol to monitor a logfile is simple, just one small change to the system's ``/var/ospatrol/etc/ospatrol.conf`` and a restart of the OSPatrol processes. Alternately, the configuration can be placed in the ``/var/ospatrol/etc/shared/agent.conf`` on the manager.

There are a number of formats that OSPatrol recognizes, the main one being ``syslog``. If there is a log format OSPatrol does not recognize, you can use ``syslog`` as a "catch-all," and build your decoders/rules around it. Other options can be found on the `localfile <../syntax/head_ospatrol_config.localfile.html>`_ syntax page.



What log files does OSPatrol monitor by default:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* ``/var/log/messages``
* ``/var/log/secure``
* ``/var/log/authlog``
* ``/var/log/xferlog``
* ``/var/log/maillog``
* ``/var/www/logs/access_log``
* ``/var/www/logs/error_log``


Additional files to monitor:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

* On Debian based systems:
  - ``/var/log/dpkg.log``

* On RHEL based systems:
  - ``/var/log/yum.log``


Monitoring /var/log/messages:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

  <ospatrol_config>

    <localfile>
      <log_format>syslog</log_format>
      <location>/var/log/messages</location>
    </localfile>

  </ospatrol_config>



Monitoring /var/log/apache/access_log:
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

  <ospatrol_config>
    <localfile>
      <log_format>apache</log_format>
      <location>/var/log/apache/access_log</location>
    </localfile>
  </ospatrol_config>


Windows localfiles:
^^^^^^^^^^^^^^^^^^^

.. code-block:: console

 <localfile>
    <location>Application</location>
    <log_format>eventlog</log_format>
  </localfile>

  <localfile>
    <location>Security</location>
    <log_format>eventlog</log_format>
  </localfile>

  <localfile>
    <location>System</location>
    <log_format>eventlog</log_format>
  </localfile>



