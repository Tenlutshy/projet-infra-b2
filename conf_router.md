### Router

```bash
# Configuration du NAT

-------------------

interface GigabitEthernet6
ip nat inside
exit

interface GigabitEthernet6.10
ip nat inside
exit

interface GigabitEthernet6.20
ip nat inside
exit

interface GigabitEthernet6.30
ip nat inside
exit

interface GigabitEthernet5
ip nat outside
exit

access-list 1 permit any

ip nat inside source list 1 interface GigabitEthernet5 overload

interface GigabitEthernet5
no shut
id address dhcp

------------------

# Configuration des interfaces

interface GigabitEthernet6.10
encapsulation dot1Q
ip addr 10.33.10.254 255.255.255.0
no shut
exit

interface GigabitEthernet6.20
encapsulation dot1Q
ip addr 10.33.20.14 255.255.255.240
no shut
exit

interface GigabitEthernet6.30
encapsulation dot1Q
ip addr 10.33.30.6 255.255.255.248
no shut
exit

```
