# Day 4 — IPv4 Addressing and Subnetting

## Objective

Understand IPv4 addressing, subnet masks, default gateways, and communication between two different networks using a Cisco router.

## Network Topology

The network consists of:

- 1 Cisco 2811 Router (R1)
- 2 Cisco 2960 Switches (SW1 and SW2)
- 2 PCs (PC-SALES and PC-IT)

The router connects two separate LANs.

## Network Design

### LAN 1 — SALES

| Device | Interface | IP Address |
|---|---|---|
| R1 | FastEthernet0/0 | 192.168.10.1 |
| PC-SALES | FastEthernet0 | 192.168.10.10 |

- Network: `192.168.10.0/24`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.10.1`

### LAN 2 — IT

| Device | Interface | IP Address |
|---|---|---|
| R1 | FastEthernet0/1 | 192.168.20.1 |
| PC-IT | FastEthernet0 | 192.168.20.10 |

- Network: `192.168.20.0/24`
- Subnet Mask: `255.255.255.0`
- Default Gateway: `192.168.20.1`

## Router Configuration

The following Cisco IOS commands were used:

```bash
enable
configure terminal

interface FastEthernet0/0
description SALES_NETWORK
ip address 192.168.10.1 255.255.255.0
no shutdown
exit

interface FastEthernet0/1
description IT_NETWORK
ip address 192.168.20.1 255.255.255.0
no shutdown
exit

end
copy running-config startup-config
```

## Verification Commands

To verify interface status and IP addresses:

```bash
show ip interface brief
```

Both router interfaces were verified as `up/up`.

To verify the router's routing table:

```bash
show ip route
```

The router automatically learned both directly connected networks.

## Connectivity Testing

Connectivity was tested using the `ping` command.

From PC-SALES:

```bash
ping 192.168.10.1
ping 192.168.20.10
```

From PC-IT:

```bash
ping 192.168.20.1
```

Successful replies confirmed connectivity to the gateways and communication between the two LANs.

## Troubleshooting

During testing, the initial ping between the two networks failed because one PC had an incorrectly configured default gateway.

The issue was resolved by correcting the default gateway address.

This demonstrated the importance of verifying IP addressing, subnet masks, and default gateway configuration when troubleshooting network connectivity.

## Key Concepts Learned

- IPv4 addressing
- Subnet masks and CIDR notation
- `/24` network prefixes
- Network, broadcast, and usable host addresses
- Default gateway configuration
- Directly connected routes
- Inter-network communication
- Basic network troubleshooting

## Project Status

Completed and verified. Successful connectivity between the SALES and IT networks was confirmed using ping tests.

## Tools

- Cisco Packet Tracer
- Cisco 2811 Router
- Cisco 2960 Switches
- Cisco IOS CLI
