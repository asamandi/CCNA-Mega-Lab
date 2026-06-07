## CCNA Enterprise Mega Lab
### Overview

This project demonstrates a complete enterprise network built in Cisco Packet Tracer. The lab combines multiple CCNA technologies into a single enterprise environment and validates connectivity, redundancy, routing, security, IPv6, and Internet access.

The goal of this project is to simulate a real-world enterprise network while practicing configuration, verification, and troubleshooting skills.

------------------------------------------------------------------
### Technologies Implemented
- VLANs
- Trunking (802.1Q)
- Inter-VLAN Routing (Router-on-a-Stick)
- HSRP (Gateway Redundancy)
- DHCP Relay (IP Helper Address)
- DHCP Services
- OSPFv2
- OSPFv3
- IPv4 Routing
- IPv6 Routing
- NAT Overload (PAT)
- IPv4 ACLs
- IPv6 ACLs
- High Availability
- Enterprise Troubleshooting

-------------------------------------------------------------------------
### Network Topology
### Routers
- R1
- R2
- R3
- ISP

### Switches
- S1

### End Devices
- PC1
- PC2
- PC3
- PC4
- PC5
- PC6
- Server1

--------------------------------------------------------------------------------
### VLAN Design
| VLAN | Name    | IPv4 Network    |
| ---- | ------- | --------------- |
| 10   | SALES   | 192.168.10.0/24 |
| 20   | HR      | 192.168.20.0/24 |
| 30   | IT      | 192.168.30.0/24 |
| 99   | SERVERS | 192.168.99.0/24 |

--------------------------------------------------------------------------------
### IPv6 Design
| VLAN | IPv6 Prefix      |
| ---- | ---------------- |
| 10   | 2001:DB8:10::/64 |
| 20   | 2001:DB8:20::/64 |
| 30   | 2001:DB8:30::/64 |
| 99   | 2001:DB8:99::/64 |

--------------------------------------------------------------------------------
### HSRP Configuration
Gateway redundancy is implemented between R1 and R2.

### Virtual Gateways
| VLAN | Virtual Gateway |
| ---- | --------------- |
| 10   | 192.168.10.1    |
| 20   | 192.168.20.1    |
| 30   | 192.168.30.1    |
| 99   | 192.168.99.1    |


### Active Routers
| VLAN | Active Router |
| ---- | ------------- |
| 10   | R1            |
| 20   | R2            |
| 30   | R2            |
| 99   | R1            |

--------------------------------------------------------------------------------
### Dynamic Routing
### OSPFv2
Configured between 
- R1
- R2
- R3.

Purpose:
- Automatic route exchange
- Faster convergence
- Simplified routing administration

### OSPFv3
- Configured for IPv6 routing.

Purpose:
- Dynamic IPv6 route exchange
- End-to-end IPv6 connectivity

--------------------------------------------------------------------------------
### DHCP Implementation
Server1 provides DHCP services for all VLANs.

### DHCP Relay

Implemented using:
- ip helper-address

Purpose:
- Forward DHCP broadcasts across routed networks
- Centralized DHCP management

--------------------------------------------------------------------------------
### NAT Overload (PAT)

Configured on R3.

Purpose:
- Allow private IPv4 networks to access external networks
- Translate multiple private addresses to a single public IP

Public Interface:
- 203.0.113.2

Internet Test Address:
- 8.8.8.8

--------------------------------------------------------------------------------
### Security Implementation
### IPv4 ACL
Blocks HTTP traffic from VLAN20 users to the internal server while allowing all other traffic.

### IPv6 ACL
Blocks IPv6 traffic originating from VLAN30 while permitting ICMPv6 traffic required for IPv6 operation.

--------------------------------------------------------------------------------
### Verification Commands
### VLANs
- show vlan brief
- show interfaces trunk

### HSRP
- show standby brief

### OSPF
- show ip ospf neighbor
- show ip route

### OSPFv3
- show ipv6 ospf neighbor
- show ipv6 route

### NAT
- show ip nat translations
- show ip nat statistics

### ACLs
- show access-lists
- show ipv6 access-list

--------------------------------------------------------------------------------
### Validation Performed
### Layer 2
- VLAN connectivity verified
- Trunk operation verified

### Layer 3
- Inter-VLAN routing verified
- OSPF route exchange verified
- OSPFv3 route exchange verified

### High Availability
- HSRP failover tested
- Gateway redundancy verified

### Services
- DHCP address assignment verified
- DHCP relay functionality verified

### Security
- IPv4 ACL functionality verified
- IPv6 ACL functionality verified

### Internet Connectivity
- NAT translations verified
- End-to-end connectivity to 8.8.8.8 verified

--------------------------------------------------------------------------------
### Troubleshooting Scenarios Tested
- DHCP failures
- Missing helper-address
- OSPF adjacency issues
- NAT translation issues
- ACL blocking traffic
- HSRP failover events
- IPv6 routing problems

--------------------------------------------------------------------------------
### Skills Demonstrated
- Cisco Router Configuration
- Cisco Switch Configuration
- Enterprise VLAN Design
- Inter-VLAN Routing
- First-Hop Redundancy Protocol (HSRP)
- Dynamic Routing (OSPFv2/OSPFv3)
- DHCP Services
- DHCP Relay
- Network Address Translation (NAT)
- Access Control Lists (ACLs)
- IPv6 Networking
- Network Troubleshooting
- Enterprise Network Operations

--------------------------------------------------------------------------------
### Project Outcome
Successfully designed, configured, verified, and troubleshot a complete enterprise network infrastructure using Cisco Packet Tracer.

This project demonstrates practical CCNA-level skills in:
- Routing
- Switching
- VLANs
- HSRP
- OSPF
- OSPFv3
- DHCP
- DHCP Relay
- NAT/PAT
- IPv4 ACLs
- IPv6 ACLs
- IPv6 Networking
- Network Troubleshooting
- Enterprise Network Operations
