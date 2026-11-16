# Small Office Network Design | Cisco Packet Tracer

A hands-on networking project that simulates a small office network with separate HR and IT subnets, DHCP-based IP address allocation, inter-subnet routing, and network troubleshooting using Cisco Packet Tracer.

## Project Overview

This project demonstrates the design, configuration, and testing of a small office network connecting two departments: Human Resources (HR) and Information Technology (IT).

The network uses a Cisco router to connect two departmental LANs through separate physical interfaces. DHCP is configured on the router to automatically assign IP addresses to client devices.

## Network Topology

**Network diagram:** See `screenshots/network-topology.png`.

## Network Devices

| Device | Quantity | Purpose |
|---|---:|---|
| Cisco Router | 1 | Routing between HR and IT |
| Cisco Switches | 2 | Connecting departmental devices |
| PCs | 6 | HR and IT client systems |
| Server | 1 | Office server with static IP |

## IP Addressing Scheme

| Department | Network | Subnet Mask | Default Gateway |
|---|---|---|---|
| HR | 192.168.10.0/24 | 255.255.255.0 | 192.168.10.1 |
| IT | 192.168.20.0/24 | 255.255.255.0 | 192.168.20.1 |

### Router Interface Configuration

| Interface | IP Address | Connected Network |
|---|---|---|
| GigabitEthernet0/0 | 192.168.10.1/24 | HR |
| GigabitEthernet0/1 | 192.168.20.1/24 | IT |

### Server Configuration

| Parameter | Value |
|---|---|
| IP Address | 192.168.20.10 |
| Subnet Mask | 255.255.255.0 |
| Default Gateway | 192.168.20.1 |

## Technologies and Concepts

- Cisco Packet Tracer
- IPv4 addressing and subnetting
- DHCP configuration and address allocation
- Default gateway configuration
- Inter-subnet routing
- ARP (Address Resolution Protocol)
- Proxy ARP
- Network connectivity testing
- Basic network troubleshooting

## DHCP Configuration

Two DHCP pools were configured on the router:

- **HR_POOL:** 192.168.10.0/24
- **IT_POOL:** 192.168.20.0/24

The first ten addresses in each subnet were excluded from dynamic allocation to reserve addresses for gateways and infrastructure.

Client PCs obtain their IP addresses, subnet masks, and default gateways automatically through DHCP.

## Network Testing

The following tests were performed:

- Verified router interfaces using `show ip interface brief`.
- Verified DHCP pools using `show ip dhcp pool`.
- Verified allocated addresses using `show ip dhcp binding`.
- Tested communication between PCs within the same subnet.
- Tested communication between HR and IT subnets.
- Tested communication between HR clients and the office server.
- Verified default gateway functionality.

## Troubleshooting Scenarios Practised

- Incorrect default gateway configuration.
- Incorrect subnet mask configuration.
- DHCP service failure and APIPA address assignment.
- DHCP address pool exhaustion.
- ARP and Proxy ARP behaviour.
- Identifying connectivity failures using ping and Packet Tracer Simulation Mode.

## How to Run the Project

1. Install Cisco Packet Tracer.
2. Clone or download this repository.
3. Open `small-office-network-design.pkt`.
4. Wait for network devices to initialize.
5. Test connectivity using the Command Prompt on the PCs.

## Project Files

```text
small-office-network-design/
├── README.md
├── small-office-network-design.pkt
└── screenshots/
    ├── network-topology.png
    ├── dhcp-configuration.png
    └── connectivity-tests.png
```

## Learning Outcomes

Through this project, I gained practical experience in:

- Designing a small office network.
- Configuring router interfaces and DHCP pools.
- Understanding subnetting and default gateways.
- Troubleshooting DHCP and connectivity issues.
- Analysing network packets using Simulation Mode.

## Author

**SONGA VENUGOPAL**

- GitHub: https://github.com/venu-3754
- LinkedIn: https://linkedin.com/in/songavenugopal

---

*This is an educational network simulation project developed using Cisco Packet Tracer.*
