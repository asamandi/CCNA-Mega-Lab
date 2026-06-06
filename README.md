VLANs + Trunking

Inter-VLAN Routing (Router-on-a-Stick)

DHCP + DHCP Relay

OSPF (IPv4 + IPv6)

NAT Overload (PAT)

ACLs (IPv4 + IPv6)

HSRP (Gateway Redundancy)

IPv6 (SLAAC + DHCPv6)

STP (Loop prevention)

WAN concepts


Routers:
---------------------------------------
R1

R2

R3 ← edge/core (does NAT)

ISP ← internet

Switch:
---------------------------------------
S1

End devices:
---------------------------------------
PC1, PC2 (VLAN10)

PC3, PC4 (VLAN20)

PC5, PC6 (VLAN30)

Server1 (DHCP + HTTP)

Cabling + Exact Interface Map:
---------------------------------------
S1

Fa0/1 → PC1 (VLAN10)

Fa0/2 → PC2 (VLAN10)

Fa0/3 → PC3 (VLAN20)

Fa0/4 → PC4 (VLAN20)

Fa0/5 → PC5 (VLAN30)

Fa0/6 → PC6 (VLAN30)

Fa0/24 → Server1 (VLAN99 Servers)

Gi0/1 ↔ R1 Gi0/0 (TRUNK)

Gi0/2 ↔ R2 Gi0/0 (TRUNK)

Core/WAN links:
---------------------------------------
R1 Gi0/1 ↔ R3 Gi0/0

2 Gi0/1 ↔ R3 Gi0/1

R3 Gi0/2 ↔ ISP Gi0/0

Addressing Plan IPv4 + IPv6
---------------------------------------
VLANs (IPv4)

| VLAN | Name    | Subnet          | HSRP Gateway |
| ---- | ------- | --------------- | ------------ |
| 10   | SALES   | 192.168.10.0/24 | 192.168.10.1 |
| 20   | HR      | 192.168.20.0/24 | 192.168.20.1 |
| 30   | IT      | 192.168.30.0/24 | 192.168.30.1 |
| 99   | SERVERS | 192.168.99.0/24 | 192.168.99.1 |


Router VLAN IPs (per VLAN):
---------------------------------------
R1 = .2

R2 = .3

HSRP virtual = .1

Example VLAN10:
---------------------------------------
R1: 192.168.10.2

R2: 192.168.10.3

VIP: 192.168.10.1

IPv6 VLAN prefixes:
---------------------------------------

| VLAN | IPv6 Prefix      | Router GW (R1) |
| ---- | ---------------- | -------------- |
| 10   | 2001:DB8:10::/64 | 2001:DB8:10::1 |
| 20   | 2001:DB8:20::/64 | 2001:DB8:20::1 |
| 30   | 2001:DB8:30::/64 | 2001:DB8:30::1 |
| 99   | 2001:DB8:99::/64 | 2001:DB8:99::1 |


Routed links (IPv4):
---------------------------------------
R1–R3: 10.0.13.0/30

R1 Gi0/1 = 10.0.13.1

R3 Gi0/0 = 10.0.13.2

R2–R3: 10.0.23.0/30

R2 Gi0/1 = 10.0.23.1

R3 Gi0/1 = 10.0.23.2

R3–ISP: 203.0.113.0/30

R3 Gi0/2 = 203.0.113.2

ISP Gi0/0 = 203.0.113.1

ISP “internet” loopback:

ISP Lo0 = 8.8.8.8/32

Routed links (IPv6):
---------------------------------------
R1–R3: 2001:DB8:13::/64

R1 Gi0/1 = 2001:DB8:13::1/64

R3 Gi0/0 = 2001:DB8:13::2/64

R2–R3: 2001:DB8:23::/64

R2 Gi0/1 = 2001:DB8:23::1/64

R3 Gi0/1 = 2001:DB8:23::2/64
