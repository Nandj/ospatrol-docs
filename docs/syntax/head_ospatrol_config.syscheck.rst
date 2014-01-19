.. _ospatrol_config.syscheck: 

ospatrol.conf: Syscheck Options
============================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Syscheck options are available in the the following installation types:

* server
* local 
* agent 

Location 
^^^^^^^^

All global options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <syscheck> 
            <!-- 
            Syscheck options here
            --> 
        </syscheck> 
    </ospatrol_config> 

Options 
------- 

.. include:: ./ospatrol_config.syscheck.trst
