# zabbix - dell - idrac

## Items

Here's a list of Applications that are monitored in this template.

TODO: detail the items, triggers and graphs

### Disks / Storage

### Fans

### Memory

### Network Cards

### Power

### System Info

### Temperatures

### Voltages

## Setup

If ou are using a Zabbix version >= 3.0, you can import the `ValueMaps_Dell_iDRAC.zbx.xml` and the choosen `Template_Dell_iDRAC_SNMPv{23}.zbx.xml` file for this to work.

If you are using a Zabbix version < 3.0, you need to create the Value Mapping prior to the import of the templates, for it to work as expected.

Menu: Administration->General->Value mapping->Create value map

Create all the following Value Mapping

* DellDracDiskState	

````
1 -> Unknown
2 -> Ready
3 -> Online
4 -> Foreign
5 -> Offline
6 -> Blocked
7 -> Failed
8 -> Non-RAID
9 -> Removed
````

* Dell iDRAC Network Device Connection Status	

````
1 -> Connected
2 -> Disconnected
````

* Dell Open Manage System Status	

````
1 -> Other
2 -> Unknown
3 -> OK
4 -> NonCritical
5 -> Critical
6 -> NonRecoverable
````

* DellPowerState	

````
1 -> Other
2 -> Unknown
3 -> Off
4 -> On
````

* Dell PSU State Settings	

````
1 -> Unknown
2 -> Online (state disabled)
4 -> not Ready
8 -> Fan Failure
10 -> Online and Fan Failure
16 -> On
242 -> Online and OK
````

* DellRaidLevel	

````
1 -> Unknown
2 -> RAID-0
3 -> RAID-1
4 -> RAID-5
5 -> RAID-6
6 -> RAID-10
7 -> RAID-50
8 -> RAID-60
9 -> Concatenated RAID 1
10 -> Concatenated RAID 5
````

* DellRaidVolumeState	

````
1 -> Unknown
2 -> Online
3 -> Failed
4 -> Degraded
````

* Dell_PSU_SensorState	

````
1 -> Presence Detected
2 -> PS Failure
4 -> Predictuve Failure
8 -> PS AC lost
16 -> AC lost or out of range
32 -> AC out of range but still present
````

## Credits

I found this template at [Zabbix Forum](https://www.zabbix.com/forum) thread [#43517](https://www.zabbix.com/forum/showthread.php?t=43517), and I'm enhancing it.xz
