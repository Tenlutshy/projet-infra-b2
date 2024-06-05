### DHCP

```bash
# DHCP Server Configuration file.
#   see /usr/share/doc/dhcp-server/dhcpd.conf.example
#   see dhcpd.conf(5) man page
# create new
# specify domain name
option domain-name     "boo.boo";
# specify DNS server's hostname or IP address
option domain-name-servers     1.1.1.1;
# default lease time
default-lease-time 600;
# max lease time
max-lease-time 7200;
# this DHCP server to be declared valid
authoritative;
# specify network address and subnetmask

subnet 10.33.10.0 netmask 255.255.255.0 {
    # specify the range of lease IP address
    range dynamic-bootp 10.33.10.1 10.33.10.253;
    # specify broadcast address
    option broadcast-address 10.33.10.255;
    # specify gateway
    option routers 10.33.10.254;
}

subnet 10.33.20.0 netmask 255.255.255.240 {
    range dynamic-bootp 10.33.10.1 10.6.3.13;
    option broadcast-address 10.33.20.15;
    option routers 10.33.20.14;
}

subnet 10.33.30.0 netmask 255.255.255.248 {
    range dynamic-bootp 10.33.30.1 10.33.30.5;
    option broadcast-address 10.33.30.7;
    option routers 10.33.30.6;
}
```
