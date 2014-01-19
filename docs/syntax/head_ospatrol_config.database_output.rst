
.. _ospatrol_config.database_output: 

ospatrol.conf: Database Output options
===================================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Database Output options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All database_output options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <database_output> 
            <!-- 
            Database Output options here
            --> 
        </database_output> 
    </ospatrol_config> 


Options
-------

.. include:: ospatrol_config.database_output.trst 
