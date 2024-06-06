### Router

```bash
# Configuration du NAT

-------------------

interface GigabitEthernet2
ip nat inside
exit

interface GigabitEthernet2.10
ip nat inside
exit

interface GigabitEthernet2.20
ip nat inside
exit

interface GigabitEthernet2.30
ip nat inside
exit

interface GigabitEthernet1
ip nat outside
exit

access-list 1 permit any

ip nat inside source list 1 interface GigabitEthernet1 overload

interface GigabitEthernet1
no shut
ip address dhcp


# Configuration des interfaces

-------------------
interface GigabitEthernet2
no shut
exit

interface GigabitEthernet2.10
encapsulation dot1Q 10
ip addr 10.33.10.254 255.255.255.0
no shut
exit

interface GigabitEthernet2.20
encapsulation dot1Q 20
ip addr 10.33.20.14 255.255.255.240
no shut
exit

interface GigabitEthernet2.30
encapsulation dot1Q 30
ip addr 10.33.30.6 255.255.255.248
no shut
exit
```
