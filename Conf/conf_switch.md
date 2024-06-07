### Switch

```bash
#Configuration des interfaces

-------------------

vlan 10
name client
exit

vlan 20
name serv
exit

vlan 30
name dhcp_ad
exit

interface Ethernet0/0
  switchport trunk encapsulation dot1q
  switchport mode trunk
  switchport trunk allowed vlan add 10,20,30
exit

interface Ethernet0/1
  switchport mode access
  switchport access vlan 20
exit

interface Ethernet0/2
  switchport mode access
  switchport access vlan 20
exit

interface Ethernet0/3
  switchport mode access
  switchport access vlan 30
exit

interface Ethernet1/0
  switchport mode access
  switchport access vlan 10
exit

interface Ethernet1/1
  switchport mode access
  switchport access vlan 10
exit

interface Ethernet1/2
  switchport mode access
  switchport access vlan 10
exit

interface Ethernet1/3
  switchport mode access
  switchport access vlan 10
exit
```
