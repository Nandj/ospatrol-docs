
.. _ospatrol_config.localfile: 

ospatrol.conf: Localfile options
=============================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Localfile options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All localfile options must be configured in the /var/ospatrol/etc/ospatrol.conf or 
/var/ospatrol/etc/shared/agent.conf and used within the <ospatrol_config> or 
<agent_config> tags.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <localfile> 
            <!-- 
            Localfile options here
            --> 
        </localfile> 
    </ospatrol_config> 


Options
-------

.. include:: ospatrol_config.localfile.trst 
