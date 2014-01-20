.. _faq_syscheck:

Syscheck: FAQ
-------------

.. contents:: 
    :local:


How to force an immediate syscheck scan?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    Run agent control tool to perform a integrity checking immediately (option 
    -a to run on all the agents and -u to specify an agent id)

    .. code-block:: console 

        # /var/ospatrol/bin/agent_control -r -a
        # /var/ospatrol/bin/agent_control -r -u <agent_id>

    For more information see the :ref:`agent_control` documentation. 

How to tell syscheck not to scan the system when OSPatrol starts?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    Set the option <scan_on_start> to “no” on ospatrol.conf 


How to ignore a file that changes too often?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    Set the file/directory name in the <ignore> option or create a simple local rule. 
    
    The following one will ignore files /etc/a and /etc/b and the directory /etc/dir 
    for agents mswin1 and ubuntu-dns:

    .. code-block:: xml 

        <rule id="100345" level="0" >
            <if_group>syscheck</if_group>
            <description>Changes ignored.</description>
            <match>/etc/a|/etc/b|/etc/dir</match>
            <hostname>mswin1|ubuntu-dns</hostname>
        </rule>

Why does OSPatrol still scan a file even though it's been ignored?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    No idea. So if there are some directories you do not want scanned at all, make sure they are not included in a ``<directories>`` configuration.

How to know when the syscheck scan ran?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    Use the agent_control tool on the manager, to see this information.

    More information see the :ref:`agent_control` documentation. 

How to get detailed reporting on the changes?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

    Use the syscheck_control tool on the manager or the web ui for that. 

    More information see the :ref:`syscheck_control` documentation. 

Syscheck not sending any file data to the server?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

With ospatrol 1.3 and Fedora you may run into this problem:

You have named files you'd like ospatrol to monitor so you add:

.. code-block:: xml 

    <ospatrol_config>
        <syscheck>
            <directories check_all="yes">/var/named</directories> 

to ospatrol.conf on the client. Fedora -- at least as of version 7 -- 
runs named in a chroot jail under /var/named/chroot. However, part of 
that chroot jail includes /var/named/chroot/proc. The contents of 
that directory are purely ephemeral; there is no value to checking 
their integrity. And, at least in ospatrol 1.3, your syscheck may stall 
trying to read those files.

The symptom is a syscheck database on the server that never grows 
beyond a file or two per restart of the client. The log monitoring continues 
to work, so you know it's not a communication issue, and you will often 
see a slight increase in syscheck database file size after the client has 
restarted (in one case about 20 minutes after). But the database will never be 
completely built; there will only be a couple files listed in datebase.

The solution is to add an ignore clause to ospatrol.conf on the client:

.. code-block:: xml

    <ospatrol_config>
        <syscheck>
            <ignore>/var/named/chroot/proc</ignore> 


Why aren't new files creating an alert?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

By default OSPatrol does not alert on new files.
To enable this functionlity, <alert_new_files> must be set to yes inside the <syscheck> section of the manager's ospatrol.conf.
Also, the rule to alert on new files (rule 554) is set to level 0 by default. 
The alert level will need to be raised in order to see the alert.
Alerting on new files does not work in realtime, a full scan will be necessary to detect them.

Add the following to local_rules.xml:

.. code-block:: xml

  <rule id="554" level="10" overwrite="yes">
    <category>ospatrol</category>
    <decoded_as>syscheck_new_entry</decoded_as>
    <description>File added to the system.</description>
    <group>syscheck,</group>
  </rule>

The ``<alert_new_files>`` entry should look something like this:

.. code-block:: xml

  <syscheck>
    <frequency>7200</frequency>
    <alert_new_files>yes</alert_new_files>
    <directories check_all="yes">/etc,/bin,/sbin</directories>
  </syscheck>


Can OSPatrol include information on who changed a file in the alert?
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

In short, no. OSPatrol does not track this information. 
You could use your OS's auditing facilities to track this information, 
and create a rule to alert when an appropriate log is created.


