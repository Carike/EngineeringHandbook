# Zabbix

https://www.zabbix.com/

## Add an agent
General overview

## Add web monitor
alert + trigger

## Dashboards

## Troubleshooting

From [My Zabbix is down, now what? Restoring Zabbix functionality](https://blog.zabbix.com/my-zabbix-is-down-now-what/28776/):

Step by step: Understanding why Zabbix is unavailable
When Zabbix becomes unavailable, it’s important to follow a few key steps to try to resolve the problem as quickly as possible.

1. **Check the service status.** First, verify if your Zabbix service is truly inactive. You can do this by accessing the machine where Zabbix is installed and checking the service status using a command like `systemctl status zabbix-server` on Linux.
1. **Analyze the Zabbix logs.** Check the Zabbix logs for any error messages or clues about what may have caused the failure.
1. **Restart the service.** 
  If the Zabbix service has stopped, try restarting it using the appropriate command for your operating system. For example, on Linux, you can use `sudo systemctl restart zabbix-server`.
1. **Check the database connectivity.**
  Zabbix uses a database to store data and Zabbix server configurations. Make sure that the database is accessible and functioning properly. You can test database connectivity using tools like ping or telnet.
1. **Check your available disk space.** 
  Verify that there is available disk space on the machine where Zabbix is installed. A lack of disk space is a common cause of system failures.
1. **Evaluate dependencies.** Make sure all Zabbix dependencies are installed and working correctly. This includes libraries, services, and any other software required for Zabbix to function.

If the problem persists after carrying out these steps, it may be necessary to refer to the official Zabbix documentation, seek help from the official Zabbix forum, or contact the Zabbix technical support team, depending on the severity and urgency of the situation.