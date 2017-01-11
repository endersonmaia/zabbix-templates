# RSTP via SNMP

This template uses a Discovery Rule to find interfaces of a switch that has RSTP enabled, and add trigger to monitor it's status. In case you only want to monitor some of the interfaces, you have to change the filter rules.

## Installing

Download the file `Template_SNMP_RSTP.zbx.xml` and import it into Zabbix.

Associate this template with all the switches that you want to enable RSTP monitoring.

## Config

If you want the Discovery Rule to act only on some ports, RSTP enabled or not on that port, add a Filter on the Discovery Rule for {$SNMPVALUE} with a regular expression of `(45|46)`. Assuming the ports 45 and 46 have RSTP enabled and working, and your interfaces have numbers in its description.

These recomendations are just to avoid creating itens that won't be used.

## Explanation

The possible states for a RSTP enabled port are :

- 1 ⇒ disabled;
- 2 ⇒ blocking;
- 3 ⇒ listening;
- 4 ⇒ learning;
- 5 ⇒ forwarding;
- 6 ⇒ broken;

If it's listening (3 - INFO) or learning (4 - INFO) before forwarding (5 - OK).

If blocking (2 - OK), means that another path is beeing used.

## References

* https://www.ietf.org/rfc/rfc1493.txt
* https://standards.ieee.org/findstds/standard/802.1D-1990.html
