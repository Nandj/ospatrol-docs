.. _ospatrol_config.client:

ospatrol.conf: Client Options
==========================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

client options are available in the the following installation types:

* agent

Location 
^^^^^^^^

All client options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <client> 
            <!-- 
            client options here
            --> 
        </client> 
    </ospatrol_config> 

Options 
------- 

.. include:: ./ospatrol_config.client.trst
