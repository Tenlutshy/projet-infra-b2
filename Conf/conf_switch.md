### Switch

**Configuration du switch**

```bash
interface Ethernet2/1
  switchport
  switchport trunk encapsulation dot1q
  switchport mode trunk
  switchport trunk allow vlan add 10,20,30

interface Ethernet2/2
  switchport
  switchport access vlan 20

interface Ethernet2/3
  switchport
  switchport access vlan 20

interface Ethernet2/4
  switchport
  switchport access vlan 30

interface Ethernet2/5
  switchport
  switchport access vlan 10

interface Ethernet2/6
  switchport
  switchport access vlan 10

interface Ethernet2/7
  switchport
  switchport access vlan 10

interface Ethernet2/8
  switchport
  switchport access vlan 10

```
