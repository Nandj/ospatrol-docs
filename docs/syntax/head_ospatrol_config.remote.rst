.. _ospatrol_config.remote: 

ospatrol.conf: Remote Options
==========================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

remote options are available in the the following installation types:

* server

Location 
^^^^^^^^

All remote options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <remote> 
            <!-- 
            remote options here
            --> 
        </remote> 
    </ospatrol_config> 

Options 
------- 

.. include:: ./ospatrol_config.remote.trst
