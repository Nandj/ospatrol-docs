
.. _ospatrol_config.global: 

ospatrol.conf: Global options
==========================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Global options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All global options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <global> 
            <!-- 
            Global options here
            --> 
        </global> 
    </ospatrol_config> 


Options
-------

.. include:: ospatrol_config.global.trst 
