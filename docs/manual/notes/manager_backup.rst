Migrating/backing up the manager
--------------------------------

If you need to migrate the manager to another system (or just want to backup the current setup), these are the files you need:

These are the two locations where the keys are saved for all the agents.

.. code-block:: console

  /var/ospatrol/etc/client.keys
  /var/ospatrol/queue/rids/ 

These are the configuration files you may want to keep 

.. code-block:: console
  /var/ospatrol/etc/*.conf
  /var/ospatrol/rules
  /var/ospatrol/etc/*.xml
  /var/ospatrol/etc/shared/agent.conf


These are the databases where we store data for the agents.

.. code-block:: console

  /var/ospatrol/queue/syscheck
  /var/ospatrol/queue/rootcheck
  /var/ospatrol/queue/fts
  /var/ospatrol/queue/agentless

Logs stored if they are needed.

.. code-block:: console

  /var/ospatrol/logs
