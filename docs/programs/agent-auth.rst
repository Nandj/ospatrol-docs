
.. _agent-auth:

agent-auth
=============

The agent-auth program is the client application used with :ref:`ospatrol-authd` to automatically add agents to an OSPatrol manager.

agent-auth argument options
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. program:: agent-auth

.. option:: -h

    Display the help message 

.. option:: -m <manager_ip>

    IP address of the manager.

.. option:: -p <port>

    Port ospatrol-authd is running on.
    **Default** 1515

.. option:: -A <agent_name>

    Agent name to be used.
    **Default** hostname

.. option:: -D

    Directory where OSPatrol is installed.
    **Default** /var/ospatrol


agent-auth example usage
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Example: Adding an agent with a hostname
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. code-block:: console

    # /var/ospatrol/bin/agent-auth -m 192.168.1.1 -p 1515 -A example-agent
    INFO: Connected to 192.168.1.1:1515
    INFO: Using agent name as: melancia
    INFO: Send request to manager. Waiting for reply.
    INFO: Received response with agent key
    INFO: Valid key created. Finished.
    INFO: Connection closed. 



