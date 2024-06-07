### Router (Cisco IOL -> i86bi_LinuxL3)

```bash
# Configuration des interfaces

-------------------

interface Ethernet0/1
no shut
exit

interface Ethernet0/1.10
encapsulation dot1Q 10
ip addr 10.33.10.254 255.255.255.0
no shut
exit

interface Ethernet0/1.20
encapsulation dot1Q 20
ip addr 10.33.20.14 255.255.255.240
no shut
exit

interface Ethernet0/1.30
encapsulation dot1Q 30
ip addr 10.33.30.6 255.255.255.248
no shut
exit

# Configuration du NAT

-------------------

interface Ethernet0/1
ip nat inside
exit

interface Ethernet0/1.10
ip nat inside
exit

interface Ethernet0/1.20
ip nat inside
exit

interface Ethernet0/1.30
ip nat inside
exit

interface Ethernet0/0
ip nat outside
exit

access-list 1 permit any

ip nat inside source list 1 interface Ethernet0/0 overload

interface Ethernet0/0
no shut
ip address dhcp
```
