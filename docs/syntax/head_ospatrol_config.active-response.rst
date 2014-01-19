.. _ospatrol_config.active-response:


ospatrol.conf: Active Response Options
===================================

Overview 
--------

Supported types 
^^^^^^^^^^^^^^^

Active-reponse options are available in the the following installation types:

* server
* local 

Configuration pieces
^^^^^^^^^^^^^^^^^^^^

There are two pieces to an active-response configuration. 
The first is the ``<command>`` section. 
This details the command to be run, and the options it will use.
There can be any number of command options.

The second is the ``<active-response>`` section.
This section defines when the command will be run.

Location 
^^^^^^^^

All active-response options must be configured in the /var/ospatrol/etc/ospatrol.conf 
and used within the <ospatrol_config> tag.  

XML excerpt to show location:

.. code-block:: xml 

    <ospatrol_config> 
        <command>
            <!--
            Command options here 
            --> 
        </command>
        <active-response> 
            <!-- 
            active-response options here
            --> 
        </active-response> 
    </ospatrol_config> 

.. include:: ./ospatrol_config.active-response.trst

