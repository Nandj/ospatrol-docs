
.. _ospatrol_config.syslog_output: 

ospatrol.conf: Syslog Output options
=================================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Syslog Output options are available in the the following installation types:

* server
* local 

Location 
^^^^^^^^

All syslog_output options must be configured in the /var/ospatrol/etc/ospatrol.conf and used within the <ospatrol_config> tag.

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <syslog_output> 
            <!-- 
            Syslog Output options here
            --> 
        </syslog_output> 
    </ospatrol_config> 


Options
-------

.. include:: ospatrol_config.syslog_output.trst 
