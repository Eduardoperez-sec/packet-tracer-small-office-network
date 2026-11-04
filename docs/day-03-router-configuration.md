# Day 3 — Basic Router Configuration

## Objective

Learn how to access Cisco IOS, configure a router interface, assign an IPv4 address, and enable the interface.

## Network Topology

- 1 Cisco 2811 router (R1)
- 1 Cisco 2960 switch (SW1)
- 2 PCs (PC-SALES and PC-IT)

## Network Addressing

| Device | IP Address | Subnet Mask |
|---|---|---|
| R1 Fa0/0 | 192.168.10.1 | 255.255.255.0 |
| PC-SALES | 192.168.10.10 | 255.255.255.0 |
| PC-IT | 192.168.10.20 | 255.255.255.0 |

Default Gateway for both PCs: `192.168.10.1`

## Router Configuration

The following Cisco IOS commands were used:

```bash
enable
configure terminal
hostname R1
interface FastEthernet0/0
description LAN_CONNECTION_TO_SW1
ip address 192.168.10.1 255.255.255.0
no shutdown
exit
end
copy running-config startup-config
```

## Verification Commands

```bash
show ip interface brief
```

The interface should display an operational status of `up/up`.

Connectivity was tested from PC-SALES using:

```bash
ping 192.168.10.1
```

## Key Concepts Learned

- Cisco IOS command-line interface (CLI)
- Privileged EXEC mode
- Global configuration mode
- Interface configuration
- IPv4 address assignment
- Enabling interfaces with `no shutdown`
- Default gateway
- Saving configurations

## Project Status

Completed as a basic router configuration lab.

## Tools

- Cisco Packet Tracer
- Cisco 2811 Router
- Cisco 2960 Switch
