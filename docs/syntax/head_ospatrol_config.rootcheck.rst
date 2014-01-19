.. _ospatrol_config.rootcheck: 

ospatrol.conf: Rootcheck options
=============================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

rootcheck options are available in the the following installation types:

* server
* local 
* agent

Location 
^^^^^^^^

All rootcheck options must be configured in the /var/ospatrol/etc/ospatrol.conf or 
/var/ospatrol/etc/shared/agents.conf and used within the <ospatrol_config> tag.  

XML excerpt to show location if part of ospatrol.conf:

.. code-block:: xml 

    <ospatrol_config> 
        <rootcheck> 
            <!-- 
            rootcheck options here
            --> 
        </rootcheck> 
    </ospatrol_config> 

XML excerpt to the Location if part of agent.conf 


.. code-block:: xml 

    <agent_config> 
        <rootcheck> 
            <!-- 
            rootcheck options here
            --> 
        </rootcheck> 
    </agent_config> 

Options
-------

.. include:: ospatrol_config.rootcheck.trst 
