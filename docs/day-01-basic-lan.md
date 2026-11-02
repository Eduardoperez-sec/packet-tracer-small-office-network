# Day 1 — Basic LAN Configuration

## Objective

Build a basic Local Area Network (LAN) using Cisco Packet Tracer and understand how devices communicate within the same network.

## Network Topology

The network consists of:

- 1 Cisco 2960 switch (SW1)
- 2 PCs (PC-SALES and PC-IT)
- Copper Straight-Through Ethernet cables

## IPv4 Addressing

| Device | IP Address | Subnet Mask |
|---|---|---|
| PC-SALES | 192.168.10.10 | 255.255.255.0 |
| PC-IT | 192.168.10.20 | 255.255.255.0 |

Default Gateway: Not configured for this initial LAN exercise.

## Configuration and Testing

1. Connected both PCs to the Cisco 2960 switch.
2. Assigned static IPv4 addresses.
3. Used the Command Prompt on PC-SALES to test connectivity with PC-IT.
4. Used the `ping` command to test communication.

## Commands Used

```bash
ping 192.168.10.20
```

## Key Concepts Learned

- Local Area Networks (LAN)
- Ethernet communication
- IPv4 addressing
- Subnet masks
- Basic connectivity testing with ICMP
- Communication within the same subnet

## Project Status

Completed as a basic networking lab.

## Tools

- Cisco Packet Tracer
- Cisco 2960 Switch
- End Devices (PCs)
