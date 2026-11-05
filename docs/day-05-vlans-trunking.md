# Day 5 – VLANs and Trunking

## Project Overview

This lab demonstrates how to configure VLANs, assign switch ports, establish a trunk link, and implement inter-VLAN routing using Router-on-a-Stick in Cisco Packet Tracer.

## Network Topology

The network consists of:
- 1 Cisco 2811 Router (R1)
- 1 Cisco 2960 Switch (SW1)
- 2 End devices (PC-SALES and PC-IT)

## VLAN Configuration

| VLAN | Name | Network | Gateway |
|---|---|---|---|
| 10 | SALES | 192.168.10.0/24 | 192.168.10.1 |
| 20 | IT | 192.168.20.0/24 | 192.168.20.1 |

Switch port assignments:

| Switch Port | Mode | VLAN |
|---|---|---|
| Fa0/1 | Access | 10 |
| Fa0/2 | Access | 20 |
| Fa0/24 | Trunk | 802.1Q |

## IP Addressing

| Device | IP Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| PC-SALES | 192.168.10.10 | 255.255.255.0 | 192.168.10.1 |
| PC-IT | 192.168.20.10 | 255.255.255.0 | 192.168.20.1 |

## Router-on-a-Stick Configuration

Router R1 uses one physical interface with two logical subinterfaces:

- FastEthernet0/0.10 – VLAN 10 (SALES)
- FastEthernet0/0.20 – VLAN 20 (IT)

Both subinterfaces use 802.1Q encapsulation and provide the default gateway for their respective VLANs.

## Verification and Testing

The following commands were used to verify the configuration:

```bash
show vlan brief
show interfaces trunk
show ip interface brief
```

Connectivity tests were performed from PC-SALES:

```bash
ping 192.168.10.1
ping 192.168.20.10
```

**Result:** Both connectivity tests were successful, with 4 packets sent and 4 packets received.

## Skills Practiced

- VLAN creation and configuration
- Access port assignment
- IEEE 802.1Q trunk configuration
- Router-on-a-Stick
- Inter-VLAN routing
- IPv4 addressing
- Network connectivity troubleshooting
- Cisco IOS verification commands

## Lab Files and Evidence

- Packet Tracer file: `../labs/day-05-vlans-trunking.pkt`
- Network topology: `../images/day-05-topology.png`
- VLAN configuration: `../images/day-05-vlan-configuration.png`
- Trunk configuration: `../images/day-05-trunk-configuration.png`
- Connectivity test: `../images/day-05-connectivity-test.png`

## Status

**Completed & Verified**
