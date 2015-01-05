Ansible Fail2Ban Role for Zimbra Mail Servers
=============================================

An ansible role for installing and configuring fail2ban specific in [Zimbra Mail Servers](http://www.zimbra.com). This role will configure a custom jail.local to identify and ban brute force treats to your webmail and mail services.

For more information on Fail2Ban, [visit the Fail2Ban website](http://www.fail2ban.org/wiki/index.php/Main_Page)

Role Variables
--------------

- fail2ban.path: path where Fail2Ban is installed on the remote host(s)
- fail2ban.filter_path: path of fail2ban filters on the remote host(s)
- fail2ban.action_path: path  of fail2ban actions on the remote host(s)
- fail2ban.pkg_state: indicates the package state [installed, latest]
- fail2ban.pkg_version: specify the specific package version you wish to install
When specifying a version, the state will be forced to installed. When omitting the variable or leaving it empty
it will install the package as specified by the state variable 
- fail2ban.service_state: indicates the service state [started, stopped]
- fail2ban.service_enabled: indicates if service needs to be enabled on boot [yes, no]
- fail2ban.config.ignoreip: IP address, CIDR or DNS host to whitelist from fail2ban
- fail2ban.config.bantime: number of seconds that a host is banned
- fail2ban.config.maxretry: number of failures before a host get banned
- fail2ban.config.findtime: A host is banned if it has generated "maxretry" during the last "findtime" seconds
- fail2ban.config.destemail: the person who will receive the fail2ban email alert
- fail2ban.config.sender: the person who will be the from in the email alert
- fail2ban.config.usedns: specifies if jails should trust hostnames in logs
- fail2ban.config.sshport: sshd service port, commonly: 22
- zimbra.logpath: Zimbra log path, commonly: /opt/zimbra/log

View the default vars - defaults/main.yml - for a more detailed example.

License
-------

GPLv3

Author Information
------------------

Kessia Pinheiro Barboza <kessiapinheiro@gmail.com>


Based on MichaelRigart.ansible-role-fail2ban.
---------------------------------------------