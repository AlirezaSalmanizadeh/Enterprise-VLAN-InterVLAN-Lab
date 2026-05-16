# Enterprise VLAN & Inter-VLAN Routing Lab CLI Guide

## Switch Configuration (S1)

### Enter Privileged Mode
```bash
enable
```

### Enter Global Configuration Mode
```bash
configure terminal
```

---

# Create VLANs

## VLAN 10 - HR
```bash
vlan 10
name HR
```

## VLAN 20 - IT
```bash
vlan 20
name IT
```

## VLAN 30 - FINANCE
```bash
vlan 30
name FINANCE
```

## VLAN 40 - GUEST
```bash
vlan 40
name GUEST
```

## VLAN 99 - NATIVE
```bash
vlan 99
name NATIVE
```

---

# Configure Access Ports

## HR PCs
```bash
interface range fa0/1-2
switchport mode access
switchport access vlan 10
```

## IT PCs
```bash
interface range fa0/3-4
switchport mode access
switchport access vlan 20
```

## FINANCE PCs
```bash
interface range fa0/5-6
switchport mode access
switchport access vlan 30
```

## GUEST PCs
```bash
interface range fa0/7-8
switchport mode access
switchport access vlan 40
```

---

# Configure Trunk Port

```bash
interface g0/1
switchport mode trunk
switchport trunk native vlan 99
```

---

# Secure Unused Ports

```bash
interface range fa0/9-24
shutdown
```

---

# Verification Commands (Switch)

```bash
show vlan brief
show interfaces trunk
show running-config
```

---

# Router Configuration (R1)

## Enter Privileged Mode
```bash
enable
```

## Enter Global Configuration Mode
```bash
configure terminal
```

---

# Enable Physical Interface

```bash
interface g0/0
no shutdown
```

---

# Configure Router-on-a-Stick

## VLAN 10 - HR
```bash
interface g0/0.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
```

## VLAN 20 - IT
```bash
interface g0/0.20
encapsulation dot1Q 20
ip address 192.168.20.1 255.255.255.0
```

## VLAN 30 - FINANCE
```bash
interface g0/0.30
encapsulation dot1Q 30
ip address 192.168.30.1 255.255.255.0
```

## VLAN 40 - GUEST
```bash
interface g0/0.40
encapsulation dot1Q 40
ip address 192.168.40.1 255.255.255.0
```

## Native VLAN
```bash
interface g0/0.99
encapsulation dot1Q 99 native
ip address 192.168.99.1 255.255.255.0
```

---

# Verification Commands (Router)

```bash
show ip interface brief
show ip route
show running-config
```

---

# Connectivity Tests

## Ping Between VLANs

Example:
```bash
ping 192.168.20.10
```

---

# Project Skills Demonstrated

- VLAN Configuration
- Inter-VLAN Routing
- Router-on-a-Stick
- Trunk Configuration
- Access Port Assignment
- VLAN Segmentation
- Cisco IOS CLI
- Enterprise Network Design

