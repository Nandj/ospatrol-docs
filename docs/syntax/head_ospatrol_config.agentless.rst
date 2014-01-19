.. _ospatrol_config.agentless:


ospatrol.conf: Agentless Options
=============================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Agentless options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All agentless options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <agentless> 
            <!-- 
            agentless options here
            --> 
        </agentless> 
    </ospatrol_config> 

Options 
------- 

.. include:: ./ospatrol_config.agentless.trst
