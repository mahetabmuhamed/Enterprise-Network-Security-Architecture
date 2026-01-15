# Enterprise-Network-Security-Architecture
**Cisco Packet Tracer v9.0.0**

---

## 📌 Overview
This project simulates a comprehensive enterprise network design using Cisco Packet Tracer v9.0.0.

The objective is to design a secure, scalable, and multi-protocol network environment that integrates:

- IPv4 and IPv6 addressing  
- Advanced switching technologies  
- Dynamic routing protocols  
- Layered security mechanisms  

The network is divided into two major domains:
- An enterprise internal IPv4-only network
- A service-oriented dual-stack (IPv4 & IPv6) network

---

## 🌐 Network Topology
### Enterprise Network Topology
<img width="968" height="443" alt="image" src="https://github.com/user-attachments/assets/20514efa-c3d2-4164-9960-9d20cd96ebba" />


---

## 🧩 Network Architecture

### 🔹 Left Side – IPv4-Only Domain
This domain represents the internal enterprise network with strict access control and centralized monitoring.

#### Addressing
- IPv4 address space: `10.11.12.0/24`

#### Features
- DHCP services  
- Dynamic routing using OSPFv2 (IPv4)  
- Centralized management and security services:
  - NTP  
  - Syslog  
  - AAA (Authentication, Authorization, Accounting)

---

### 🔹 Right Side – Dual-Stack (IPv4 & IPv6) Domain
This domain supports both IPv4 and IPv6 connectivity and hosts enterprise application services.

#### Addressing
- IPv6 prefix: `2000:12:34::/64`  
- IPv6 configuration using SLAAC & Stateless DHCP for IPv6 clients 
- IPv4 addressing for routing and service reachability  

#### Routing
- OSPFv2 for IPv4  
- No OSPFv3 deployment  
- IPv6 connectivity via IPv6 tunneling over IPv4  

#### Enterprise Services
- DNS Server (Name Resolution)  
- Web Server (HTTP / HTTPS)  
- Mail Server (SMTP / POP3)  
- FTP Server (File Transfer)  

All services are securely reachable based on defined security policies.

---

## 🔐 Security and Connectivity Features

### Layer 2 Security
- VLAN segmentation (User, Management, Trunk)  
- 802.1X authentication  
- Port Security  
- DHCP Snooping  
- Dynamic ARP Inspection (DAI)  
- Spanning Tree Protocol (STP) security:
  - PortFast  
  - BPDU Guard  
- Blackhole VLAN for unused ports  

---

### Layer 3 & Perimeter Security
- Zone-Based Policy Firewall (ZBF)  
- Access Control Lists (ACLs)  
- IOS Intrusion Prevention System (IPS)  
- Cisco ASA Firewall for DMZ protection  
- Secure wireless access using WPA2 / WPA3  

---

### Management and AAA Security
- AAA authentication using:
  - TACACS+  
  - RADIUS  
  - Local authentication (fallback)  
- Role-Based Access Control (RBAC)  
- Customized privilege levels for administrative separation  

---

### Inter-Site and IPv6 Connectivity
- Site-to-Site IPSec VPN over IPv4 between R4 and R6  
- Encrypted inter-domain communication  
- IPv6 tunneling across IPv4-only routed backbone  
- End-to-end IPv6 communication between domains  

---

## 🎯 Project Objectives

### Establish a Dual-Stack Network Environment
- Deploy IPv4 addressing (10.11.12.0/24) across all routers and inter-router links  
- Implement IPv6 addressing (2000:12:34::/64) on right-side routers Branch2 (R1,R2,R3)  
- Configure DHCP for IPv4 hosts  
- Configure SLAAC for IPv6 hosts  
- Enable IPv6 tunneling over IPv4  

---

### Implement Secure Layer 2 Switching
- Configure VLANs for user, management, and trunk traffic  
- Apply Layer 2 security features:
  - 802.1X authentication  
  - Port Security  
  - DHCP Snooping  
  - Dynamic ARP Inspection (DAI)  
  - STP security (PortFast, BPDU Guard)  
- Isolate unused switch ports into a blackhole VLAN  

---

### Configure Dynamic Routing
- Deploy OSPFv2 (IPv4) on the left-side network  
- Use OSPFv2 where required on the right-side network  
- Achieve IPv6 routing via tunneling mechanisms  
- Configure static routing for networks behind the ASA firewall  

---

### Deploy Core Network Services
- Configure an authenticated NTP server for the left-side network  
- Configure a Syslog server for centralized logging  
- Configure Router R5 as an NTP Master (right-side)  
- Deploy enterprise servers:
  - DNS Server  
  - Web Server (HTTP / HTTPS)  
  - Mail Server (SMTP / POP3)  
  - FTP Server  

---

### Strengthen Network Defense
- Configure ZBF on Branch1-Edge to control:
  - ICMP  
  - HTTP / HTTPS  
  - DNS  
  - FTP  
- Deploy IOS IPS on ISP Router with stateful inspection  
- Apply IPv6 ACLs on Branch2-R2 to restrict unauthorized IPv6 inter-VLAN traffic  
- Configure Cisco ASA firewall policies:
  - INSIDE → DMZ (controlled internal access)  
  - OUTSIDE → DMZ (authorized public services only)  

---

## 🧰 Tools and Technologies
- Cisco Packet Tracer 9.0.0  
- Cisco IOS Routers and Switches  
- Cisco ASA Firewall  
- IPv4 / IPv6 Dual-Stack Networking  
- IPSec VPN  

---

## 📂 Repository Contents
- Packet Tracer topology file  
- Router and switch configuration files  
- Documentation and network diagrams
