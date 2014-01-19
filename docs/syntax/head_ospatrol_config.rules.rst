.. _ospatrol_config.rules: 


ospatrol.conf: Rules options
=========================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Rules options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All global options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <rules> 
            <!-- 
            Rules options here
            --> 
        </rules> 
    </ospatrol_config> 


Options
-------

.. include:: ospatrol_config.rules.trst 
