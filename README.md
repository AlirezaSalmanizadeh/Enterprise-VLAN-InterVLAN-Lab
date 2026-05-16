# 🖧 Enterprise VLAN & Inter-VLAN Routing Lab

## 🧩 Overview

This project demonstrates enterprise-level VLAN segmentation and Inter-VLAN Routing using Cisco Packet Tracer.

The lab simulates a small company environment where multiple departments are separated into different VLANs while maintaining communication between them using Router-on-a-Stick architecture.

---

# 🏢 Scenario

A company requires network segmentation between departments for better performance, security, and management.

Departments included in this lab:

- HR
- IT
- Finance
- Guest

Each department operates in its own VLAN.

---

# 🖧 Network Topology

![Topology](topology/topology.png)

---

# 🌐 VLAN Design

| VLAN ID | Department | Network |
|--------|-------------|----------|
| 10 | HR | 192.168.10.0/24 |
| 20 | IT | 192.168.20.0/24 |
| 30 | Finance | 192.168.30.0/24 |
| 40 | Guest | 192.168.40.0/24 |
| 99 | Native VLAN | 192.168.99.0/24 |

---

# 💻 IP Addressing

| Device | IP Address | Gateway |
|--------|-------------|----------|
| PC1 | 192.168.10.10 | 192.168.10.1 |
| PC2 | 192.168.10.11 | 192.168.10.1 |
| PC3 | 192.168.20.10 | 192.168.20.1 |
| PC4 | 192.168.20.11 | 192.168.20.1 |
| PC5 | 192.168.30.10 | 192.168.30.1 |
| PC6 | 192.168.30.11 | 192.168.30.1 |
| PC7 | 192.168.40.10 | 192.168.40.1 |
| PC8 | 192.168.40.11 | 192.168.40.1 |

---

# 🔧 Technologies Used

- Cisco Packet Tracer
- Cisco IOS CLI
- VLAN
- Inter-VLAN Routing
- Router-on-a-Stick
- Trunk Ports
- Access Ports
- Native VLAN
- Network Segmentation

---

# 🔥 Features Implemented

- VLAN segmentation
- Trunk configuration
- Inter-VLAN communication
- Router-on-a-Stick architecture
- Native VLAN configuration
- Access port assignment
- Department-based network isolation
- Shutdown unused switch ports

---

# ⚙️ Switch Configuration Summary

- Created VLANs for departments
- Assigned access ports to VLANs
- Configured trunk port toward router
- Configured native VLAN
- Secured unused interfaces

---

# 🌍 Router Configuration Summary

- Configured subinterfaces
- Applied 802.1Q encapsulation
- Assigned gateway IP addresses
- Enabled Inter-VLAN Routing

---

# 🧪 Verification Commands

`bash
show vlan brief
show interfaces trunk
show ip interface brief
show ip route