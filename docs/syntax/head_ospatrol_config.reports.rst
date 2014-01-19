
.. _ospatrol_config.reports: 

ospatrol.conf: Reports options
==========================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Reports options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All reports options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <reports> 
            <!-- 
            Reports options here
            --> 
        </reports> 
    </ospatrol_config> 


Options
-------

.. include:: ospatrol_config.reports.trst 
