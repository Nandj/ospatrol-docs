.. _ospatrol_config.email_alerts: 

ospatrol.conf: Granular Email options
==================================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Global options are available in the the following installation types:

* server
* local 

Notes
^^^^^

`Global email configuration <./head_ospatrol_config.global.html>`_ is necessary to use the granular email options.


Location 
^^^^^^^^

All global options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <email_alerts> 
            <!-- 
            Email_alerts options here
            --> 
        </email_alerts> 
    </ospatrol_config> 


Options
-------

.. include:: ospatrol_config.email_alerts.trst


Examples
--------

.. include:: example_ospatrol_config.email_alerts.trst
