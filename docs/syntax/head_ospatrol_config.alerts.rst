.. _ospatrol_config.alerts:


ospatrol.conf: Alerts Options
==========================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Alerts options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All alerts options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <alerts> 
            <!-- 
            alerts options here
            --> 
        </alerts> 
    </ospatrol_config> 

Options 
------- 

.. include:: ./ospatrol_config.alerts.trst
