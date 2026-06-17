# 🏢 Enterprise Network Redesign for Multi-Branch Architecture

> A simulated enterprise network redesign featuring Site-to-Site IPsec IKEv2 VPN,
> centralized monitoring, automated backups, and secure multi-branch connectivity — built in EVE-NG.

---

## 📖 Overview

This repository contains the full design, configuration, and documentation of a simulated
**multi-branch enterprise network** built in EVE-NG as part of the IT Capstone Project at
**Bahrain Polytechnic**.

The project redesigns the existing HQ network and extends it to a **new branch** using a
**Site-to-Site IPsec IKEv2 VPN**, with OSPF as the internal routing protocol, centralized
monitoring via **PRTG** and **Graylog**, automated backups using **Ansible**, and identity
management through **Active Directory**. The design prioritizes security, scalability, and
operational efficiency across both sites.

---

## 🗺️ Network Topology

![Network Topology](Documentation/Network_Topology.png)


---

## ✨ Key Features

| Feature | Details |
|---|---|
| **Site-to-Site VPN** | IPsec IKEv2 tunnel between HQ and new branch |
| **Internal Routing** | OSPF for dynamic routing within each site |
| **Static Routes** | Inter-site and gateway-level static routing |
| **Firewall & Security** | Cisco ASA with ACLs and VPN-Filters for traffic control |
| **Network Monitoring** | PRTG for device/performance monitoring, Graylog for log management |
| **Automation** | Ansible playbooks for scheduled configuration backups |
| **Identity Management** | Windows Active Directory with Role-Based Access Control (RBAC) |
| **SNMP** | Device polling and trap collection for centralized visibility |
| **Simulation Platform** | EVE-NG with Cisco IOSv, ASA, Linux, and Windows Server images |

---

## 📁 Repository Structure

```
├── Ansible/
|   ├── backups/
│   ├── group_vars/
│   ├── host_vars/
│   ├── playbooks/
│   ├── vault/
│   └── inventory.ini
|   └── ansible.cfg
├── Configurations/
│   ├── HQ/
│   ├── Branch/
│   ├── ISP/
├── Documentation/
│   ├── IP Address Table.pdf
│   ├── Network Design Document.pdf
│   └── Topology.png
├── Monitoring/
│   ├── PRTG/
│   └── Graylog/
├── Show Run/
│   ├── HQ/
│   ├── Branch/
│   ├── ISP/
├── Windows Server
└── EVE-NG.uml

```

---

## 🔧 What's Included

### 1. Network Configurations
Full CLI configurations for every device in the topology:
- **HQ & Branch routers** — OSPF, static routes, IPsec IKEv2 VPN, QoS policies
- **Layer 2/3 switches** — VLANs, inter-VLAN routing, STP
- **Cisco ASA firewalls** — ACLs, VPN-Filters, NAT, inspection policies
- **SNMP configuration** — Community strings, trap receivers, polling setup

### 2. Ansible Automation
- Playbooks for automated backup of routers, switches, and firewalls
- Inventory files for both HQ and branch devices

### 3. Monitoring Setup
- **PRTG** — PRTG Installing & Configuration, Sensor configuration for device availability
- **Graylog** — Graylog Installation & Configuration, Syslog ingestion, dashboards

### 4. Active Directory Server
- Windows Server AD configuration with RBAC for admin/user roles
- DNS and DHCP integration

### 5. EVE-NG Topology File
- Complete `.unl` lab file — ready to import directly into EVE-NG
- All device roles, VLANs, and links pre-configured

### 6. Network Design Documentation
- Full IP addressing plan (HQ, branch, management, VLANs)
- Routing protocol design covering OSPF neighborship, area design, and static route placement
- Layer 2 security controls including port security, VLAN segmentation, and STP protection
- Layer 3 security controls covering ACLs, VPN-Filters, and firewall traffic policies

---

## 🚀 How to Use This Repository

### Option A — Study & Review
1. Start with the **Network Topology** diagram to understand the overall infrastructure.
2. Read the **Network Design Document** for IP plans, VLAN design, and VPN architecture.
3. Browse device configs to understand how IPsec, OSPF, ACLs, and VPN-Filters interact.
4. Review Ansible playbooks to understand the backup automation workflow.

### Option B — Lab Reproduction
1. Install and launch **EVE-NG** (Community or Pro).
2. Import `Enterprise-Network.unl` into your EVE-NG lab folder.
3. Assign the correct **Cisco IOSv**, **ASA**, **Linux**, and **Windows Server** images.
4. Boot devices and load configs from the `Configurations/` folder.
5. Deploy Ansible on the Linux server and run the playbooks.
6. Configure PRTG and Graylog using the setup guides in `Monitoring/`.
7. Verify the network using the commands below.

---

## ✅ Verification Commands

```bash
# IPsec VPN status
show crypto isakmp sa
show crypto ipsec sa
show crypto session

# OSPF routing
show ip ospf neighbor
show ip route ospf

# Static routes
show ip route static

# ACL hits and VPN-Filters
show access-list
show ip access-lists

# SNMP
show snmp
show snmp community
```

---

## 🛠️ Tools & Technologies

| Category | Tool / Technology |
|---|---|
| Simulation | EVE-NG |
| Routers & Switches | Cisco IOSv |
| Firewall | Cisco ASA |
| VPN | IPsec IKEv2 Site-to-Site |
| Routing | OSPF + Static Routes |
| Security | ACLs, VPN-Filters |
| Monitoring | PRTG Network Monitor |
| Log Management | Graylog |
| Device Polling | SNMP |
| Automation | Ansible |
| Identity Management | Windows Active Directory |
| Server OS | Linux & Windows |

---

## 📚 Learning Objectives

This project demonstrates:
- How enterprises design **secure multi-branch networks** using IPsec IKEv2 VPN
- How to apply **defense-in-depth** using ASA firewalls, ACLs, and VPN-Filters
- The role of **OSPF** as an internal dynamic routing protocol
- How **Ansible** automates repetitive network operations and reduces human error
- How **PRTG** and **Graylog** provide full-stack observability across a network
- How **Active Directory** enforces role-based access in a Windows environment
- How **SNMP** integrates with monitoring platforms for real-time device visibility
- How to apply **QoS** to prioritize critical business traffic between sites

---

## ⚙️ System Requirements (EVE-NG Host)

| Component | Specification |
|---|---|
| OS | EVE-NG (Ubuntu-based) |
| CPU | Intel i7-12700 or equivalent |
| RAM | 32 GB |
| Storage | 500 GB SSD |

---

## 👤 Author

**Hasan Bahzad**  
Bachelor of ICT — Networking  
Bahrain Polytechnic
