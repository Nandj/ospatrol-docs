Disconnected Agent Alert
------------------------

In certain circumstances, OSPatrol may not alert on disconnected agents.  By putting this line in root's crontab(1), an alert will be sent for any disconnected agents, but only if there is at least one:

.. code-block:: console
  15,30,45,59 * * * * /var/ospatrol/bin/list_agents -n | grep -q "No agent available" || /var/ospatrol/bin/list_agents -n | mail -s "Disconnected OSPatrol Agents" user@example.com

Replace the path to OSPatrol and the e-mail address with values suitable to your installation.

(1) This needs to be done as root, however since OSPatrol will immediately chroot and drop privileges the software executes it safely.  It will run every fifteen minutes.  Adjust to suit your own tolerance.  This is one line; watch for wrapping.


