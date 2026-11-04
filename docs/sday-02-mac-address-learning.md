# Day 2 — MAC Address Learning

## Objective

Understand how a Cisco Layer 2 switch learns MAC addresses and uses its MAC address table to forward Ethernet frames.

## Network Topology

This lab uses the basic LAN created in Day 1:

- 1 Cisco 2960 switch (SW1)
- 2 PCs (PC-SALES and PC-IT)
- Ethernet connections

## Lab Procedure

1. Accessed the switch CLI.
2. Entered privileged EXEC mode.
3. Displayed the MAC address table.
4. Generated network traffic by sending a ping from PC-SALES to PC-IT.
5. Checked the MAC address table again to observe learned MAC addresses.

## Cisco IOS Commands

```bash
enable
show mac address-table
```

## Key Concepts Learned

- MAC addresses identify network interfaces at Layer 2.
- Switches learn MAC addresses by examining the source MAC address of incoming Ethernet frames.
- The MAC address table associates learned MAC addresses with switch ports and VLANs.
- When a destination MAC address is unknown, the switch floods the frame out other ports in the same VLAN, except the port where it arrived.
- A switch uses its MAC address table to forward frames.

## Important Observation

A switch does not initially know every device's MAC address. It learns addresses dynamically as devices send traffic through its ports.

## Tools

- Cisco Packet Tracer
- Cisco 2960 Switch
- Cisco IOS CLI

## Project Status

Completed as a networking learning lab.
