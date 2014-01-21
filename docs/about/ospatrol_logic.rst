.. _ospatrol_logic:

OSPatrol Processes and Data
========================

+-----------------------+--------------------------------------------------------------------------------+
| Module                | Suposition                                                                     |
+=======================+================================================================================+
| ospatrol-analysisd    | Master program. Analyzes data from the logs, syscheck,rootcheck, etc.          |
|                    | Runs as an unprivileged (ospatrol) user under chroot.                             |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-execd        | Execute active responses by calling the configured scripts. Runs as root.      |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-maild        | Send e-mail alerts. Runs as an unprivileged user (ospatrolm) under chroot.     |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-remoted      | Server side socket for server/client communications.                           |
|                       | Runs as an unprivileged user (ospatrolr) under chroot.                         |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-agentd       | Agent side socket for server/client communications.                            |
|                       | Runs as an unprivileged user (ospatrol) under chroot.                          |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-logcollector | Monitor log files and windows event logs (do not use tail).                    |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-syscheckd    | Does integrity checking and rootkit detection (rootcheck is a module of it).   |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-csyslogd     | Client syslog tool to forward OSPatrol alerts to remote syslog servers         |
|                       | (including SIM/SEMs and log management systems).                               |
+-----------------------+--------------------------------------------------------------------------------+
| ospatrol-monitord     | Monitor agent connectivity and compress daily log files.                       |
+-----------------------+--------------------------------------------------------------------------------+

*  ospatrol-logcollector on agent machine tails log file & sends to ospatrol-agent.
*  ospatrol-agent routes the information to the ospatrol-server (on server system).
*  ospatrol-remoted receives data, uncompress and unencrypt it and sends to analysysd.
*  ospatrol-analysisd detects an actionable issue.
*  ospatrol-analysisd actions:

  *  ospatrol-analysisd sends information to ospatrol-execd (if response is configured to run in the server side).
  *  ospatrol-analysisd sends information to ospatrol-remoted (if response is configured to run in the agent). 

*  ospatrol-maild monitors analysisd and generate e-mail alert.
*  If active response is enabled on the agent, ospatrol-remoted on the manager sends the active response 
   to ospatrol-agent on the agent and ospatrol-agent sends it to ospatrol-execed.
*  ospatrol-execd calls an active response script 
