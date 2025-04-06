# Small-Company-Office-Network

## 📘 Project Overview

This project demonstrates a **small business network** setup using:
- **2 VLANs (Virtual Local Area Networks)** to segment different departments
- **Router-on-a-Stick** configuration for inter-VLAN routing
- **DHCP configuration** on the router to dynamically assign IP addresses
- Departmental isolation with centralized communication via switches and router

## 🛠 Technologies & Tools
- Cisco Packet Tracer
- Networking concepts: VLAN, DHCP, Router-on-a-Stick
- Devices: Router, Switches, PCs, Printers

## 🧩 Network Structure

| VLAN | Department  | Devices                     | Color            |
|------|-------------|-----------------------------|------------------|
| 10   | IT Teams    | PC1, PC2, PC5, PC6 + Printers | Cyan (Light Blue) |
| 20   | Sales Teams | PC3, PC4, PC7, PC8 + Printers | Pink             |

Each team is divided as follows:
- **IT Team 1 & Sales Team 1**: Connected to **Switch0**
- **IT Team 2 & Sales Team 2**: Connected to **Switch1**

Both switches are connected to a **Router** using a **trunk port**, enabling **Router-on-a-Stick** for routing between VLANs.

## 🔧 Key Configurations

### 🔹 VLAN Configuration
Each switch has:
- VLAN 10: Assigned to IT team ports
- VLAN 20: Assigned to Sales team ports
- Trunk port connecting to the router

### 🔹 Router-on-a-Stick
Sub-interfaces on the router:
```bash
interface FastEthernet0/0.10
 encapsulation dot1Q 10
 ip address 192.168.10.1 255.255.255.0

interface FastEthernet0/0.20
 encapsulation dot1Q 20
 ip address 192.168.20.1 255.255.255.0
