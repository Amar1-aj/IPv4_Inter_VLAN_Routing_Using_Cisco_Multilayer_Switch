# IPv4 Inter-VLAN Routing Using Cisco Multilayer Switch

## Project Overview

This project demonstrates IPv4 Inter-VLAN Routing using a Cisco Multilayer Switch in Cisco Packet Tracer.

The network is divided into separate VLANs for Students and Staff. A Multilayer Switch (MLS) is configured with Switched Virtual Interfaces (SVIs) to enable communication between different VLANs without requiring an external router.

## Project Objectives

- Configure multiple VLANs on Cisco switches.
- Assign switch ports to their respective VLANs.
- Configure trunk links between switches.
- Implement Native VLAN configuration.
- Configure IPv4 addresses on SVIs.
- Enable IP routing on the Multilayer Switch.
- Establish communication between different VLANs.

## Network Devices Used

| Device | Quantity |
|---|---:|
| Cisco Multilayer Switch | 1 |
| Cisco Layer 2 Switch | 1 |
| Student PCs | 2 |
| Staff PCs | 2 |

## VLAN Configuration

| VLAN ID | VLAN Name | Purpose |
|---|---|---|
| 100 | Students | Student Network |
| 200 | Staff | Staff Network |
| 250 | Native | Native VLAN |
| 300 | Unused | Unused Switch Ports |

## IP Addressing Scheme

### VLAN 100 – Students

| Device | IPv4 Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| Student-PC1 | 10.10.10.126 | 255.255.255.128 | 10.10.10.1 |
| Student-PC2 | 10.10.10.125 | 255.255.255.128 | 10.10.10.1 |

**SVI Gateway:** 10.10.10.1/25

### VLAN 200 – Staff

| Device | IPv4 Address | Subnet Mask | Default Gateway |
|---|---|---|---|
| Staff-PC1 | 10.10.10.254 | 255.255.255.128 | 10.10.10.129 |
| Staff-PC2 | 10.10.10.253 | 255.255.255.128 | 10.10.10.129 |

**SVI Gateway:** 10.10.10.129/25

## Network Configuration

### 1. Layer 2 Switch (S1)

- Configured VLAN 100 for Students.
- Configured VLAN 200 for Staff.
- Configured VLAN 250 as Native VLAN.
- Configured VLAN 300 for unused ports.
- Assigned access ports to the appropriate VLANs.
- Configured unused interfaces to shutdown.
- Configured trunking on GigabitEthernet 0/1.
- Allowed VLANs 100, 200 and 250 on the trunk.

### 2. Multilayer Switch (MLS)

- Created VLANs 100, 200, 250 and 300.
- Configured unused ports in VLAN 300 and administratively shut them down.
- Enabled Layer 3 routing using the `ip routing` command.
- Configured SVI for VLAN 100 with IP address 10.10.10.1/25.
- Configured SVI for VLAN 200 with IP address 10.10.10.129/25.
- Configured trunking on GigabitEthernet 0/1.
- Configured Native VLAN 250.
- Allowed VLANs 100, 200 and 250 on the trunk.

## Key Networking Concepts Implemented

- Virtual LAN (VLAN)
- VLAN Segmentation
- Access Port Configuration
- Trunk Port Configuration
- Native VLAN
- Switched Virtual Interfaces (SVI)
- IPv4 Addressing and Subnetting
- Inter-VLAN Routing
- Layer 3 Switching
- Network Troubleshooting

## Verification Commands

The following commands can be used to verify the network configuration:

```bash
show vlan brief
show interfaces trunk
show ip interface brief
show ip route
show running-config
show ip route connected
```

### Connectivity Testing

Use the following commands from the PCs:

```bash
ping 10.10.10.1
ping 10.10.10.129
ping 10.10.10.254
```

Test communication between Student and Staff networks to verify Inter-VLAN Routing.

## Expected Project Outcome

Successful communication between Student and Staff VLANs through the Cisco Multilayer Switch using SVI-based IPv4 Inter-VLAN Routing.

## Tools Used

- Cisco Packet Tracer
- Cisco IOS CLI
- IPv4 Networking

## Conclusion

This project provides practical experience in configuring VLANs, trunk links, IPv4 addressing and Inter-VLAN Routing using a Cisco Multilayer Switch. It demonstrates how Layer 3 switching enables communication between multiple logically separated networks.

