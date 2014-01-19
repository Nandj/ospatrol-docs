
.. _ospatrol-authd:

ospatrol-authd
=============

The ospatrol-authd daemon will automatically add an agent to an OSPatrol manager and provide the key to the agent.
The :ref:`agent-auth` application is the client application used with ospatrol-authd. 
`ospatrol-authd` will create an agent with an ip address of `any` instead of using its actual IP.

There is no authentication involved in this transaction, so it is recommended that this daemon only be run when a new agent is being added.

ospatrol-authd argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: ospatrol-authd

.. option:: -d

    Run in debug mode.

.. option:: -i

    Add agents with a specific IP address instead of using ``any``.

.. option:: -p <port>

   Listen on port.

   **Default** 1515


Creating SSL keys
~~~~~~~~~~~~~~~~~

``ospatrol-authd`` requires SSL keys to run. This process will create the necessary keys in ``/var/ospatrol/etc`` and allow ``ospatrol-authd`` to start:

.. code-block:: console

  # openssl genrsa -out /var/ospatrol/etc/sslmanager.key 2048
  # openssl req -new -x509 -key /var/ospatrol/etc/sslmanager.key -out /var/ospatrol/etc/sslmanager.cert -days 365


Without the key ``ospatrol-authd`` will give the following error:

.. code-block:: console

  [user@ospatrol-manager] :; sudo /var/ospatrol/bin/ospatrol-authd  
  2012/04/18 11:05:01 ospatrol-authd: INFO: Started (pid: 20669).
  2012/04/18 11:05:01 ospatrol-authd: ERROR: Unable to read certificate file (not found): /var/ospatrol/etc/sslmanager.cert
  2012/04/18 11:05:01 ospatrol-authd: ERROR: SSL error. Exiting.



ospatrol-authd example usage
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Example: Running ospatrol-authd
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

    # /var/ospatrol/bin/ospatrol-authd -p 1515 >/dev/null 2>&1 &

And the logs when an agent is added:

.. code-block:: console

    2011/01/19 15:04:40 ospatrol-authd: INFO: New connection from 192.168.10.5
    2011/01/19 15:04:41 ospatrol-authd: INFO: Received request for a new agent (example-agent) from: 192.168.10.5
    2011/01/19 15:04:41 ospatrol-authd: INFO: Agent key generated for example-agent (requested by 192.168.10.5)
    2011/01/19 15:04:41 ospatrol-authd: INFO: Agent key created for example-agent (requested by 192.168.10.5) 


