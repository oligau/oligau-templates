# Configurations to enable SNMP on Mikrotik
Add these lines to your Mikrotik RouterBoard configuration. Limits SNMP answers by source IP and by community string. Disables default public community.

/snmp
set enabled=yes
/snmp community
set [ find default=yes ] addresses=<IPv4-of-monitoring-server>/32 name=<long-random-passphrase>

Based on andyzasl's template
https://github.com/andyzasl/zabbix-templates/blob/master/mikrotik/Mikrotik_SNMP.xml
Added SNMP_COMMUNITY macro and replaced SNMPv1 by SNMPv2c. Also removed valuemaps to enable clean importing.
