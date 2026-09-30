# Campus Network Design & Simulation

A secure and scalable campus network designedو simulated using **Cisco Packet Tracer** 

## Network Topology

![Campus network topology](https://ibb.co/qFp6tq1N)

## 📌 Project Overview

This project focuses on designing and simulating a secure and scalable campus network for a college consisting of three physically separated buildings:

* **Main Building**
* **Building 1**
* **Building 2**

The network is designed to support approximately **100 users** and provide both wired and wireless connectivity across all buildings through centralized internet access.

Each building includes a lobby requiring secure wireless network access restricted to authorized users.

---

## 🎯 Project Objectives

* Design a scalable campus network supporting approximately 100 users.
* Connect three physically separated buildings.
* Divide the network into separate subnets for each building.
* Implement three VLANs within each building for logical network segmentation.
* Provide secure wireless connectivity for authorized users.
* Enable communication between buildings.
* Implement efficient IP addressing using the `192.168.0.0/16` address range.
* Provide centralized internet access through NAT.
* Improve network reliability and prevent switching loops.

---

## 🏗️ Network Architecture

The network follows a hierarchical design in which the **Main Building acts as the central/core node**.

Each building contains:

* Access switches for wired users
* Wireless access points in lobby areas
* VLANs for logical user segmentation
* Routing functionality for inter-VLAN communication

The Main Building provides centralized connectivity to Building 1 and Building 2 through high-speed links and provides shared internet access.

---

## 🌐 Network Technologies

| Technology              | Purpose                                          |
| ----------------------- | ------------------------------------------------ |
| **VLAN**                | Logical separation of users and network segments |
| **OSPF**                | Dynamic routing between network segments         |
| **STP**                 | Prevention of Layer 2 switching loops            |
| **DHCP**                | Automatic IP address allocation                  |
| **DNS**                 | Domain/name resolution                           |
| **NAT**                 | Internet connection sharing                      |
| **Wireless Networking** | Wireless access for authorized users             |

> RIP is supported by the router for basic routing functionality; however, 
due to its slow convergence and hop-count limitation, it is not preferred for 
the campus network

---

## 🗺️ IP Addressing Design

The overall network uses the following address range:

**Base Network:** `192.168.0.0/16`

Each building receives a dedicated `/24` subnet, which is further divided into `/26` subnets for its VLANs.

### Building Subnets

| Building      | Network          | VLANs           |
| ------------- | ---------------- | --------------- |
| Main Building | `192.168.1.0/24` | VLAN 10, 11, 12 |
| Building 1    | `192.168.2.0/24` | VLAN 20, 21, 22 |
| Building 2    | `192.168.3.0/24` | VLAN 30, 31, 32 |

### Main Building

| VLAN    | Purpose  | Subnet             | Gateway         |
| ------- | -------- | ------------------ | --------------- |
| VLAN 10 | Staff    | `192.168.1.0/26`   | `192.168.1.1`   |
| VLAN 11 | Students | `192.168.1.64/26`  | `192.168.1.65`  |
| VLAN 12 | Wireless | `192.168.1.128/26` | `192.168.1.129` |

### Building 1

| VLAN    | Purpose  | Subnet             | Gateway         |
| ------- | -------- | ------------------ | --------------- |
| VLAN 20 | Staff    | `192.168.2.0/26`   | `192.168.2.1`   |
| VLAN 21 | Students | `192.168.2.64/26`  | `192.168.2.65`  |
| VLAN 22 | Wireless | `192.168.2.128/26` | `192.168.2.129` |

### Building 2

| VLAN    | Purpose  | Subnet             | Gateway         |
| ------- | -------- | ------------------ | --------------- |
| VLAN 30 | Staff    | `192.168.3.0/26`   | `192.168.3.1`   |
| VLAN 31 | Students | `192.168.3.64/26`  | `192.168.3.65`  |
| VLAN 32 | Wireless | `192.168.3.128/26` | `192.168.3.129` |

---

## 🔧 Implementation Methodology

The network was implemented through the following stages:

1. Installed the core router and core switch in the Main Building.
2. Established links between the three buildings.
3. Configured VLANs on the switches.
4. Configured trunk links between switches.
5. Configured OSPF for dynamic routing.
6. Implemented NAT for centralized internet access.
7. Configured DHCP and DNS services.
8. Configured wireless access for the building lobbies.
9. Tested network connectivity and functionality.
10. Troubleshot the simulated network to verify the configuration.

---

## ✔️ Testing

The completed network was tested using Cisco Packet Tracer to verify:

* Connectivity between devices within the same VLAN.
* Inter-VLAN communication.
* Communication between buildings.
* OSPF route propagation.
* DHCP address allocation.
* DNS resolution.
* NAT functionality.
* Wireless connectivity.
* STP operation and loop prevention.

---

## 🖥️ Project File

The complete Cisco Packet Tracer simulation is available in:

`Campus-Network-Design.pkt`

The `.pkt` file can be opened using **Cisco Packet Tracer**.

---

## 🛠️ Tools

* Cisco Packet Tracer
* IP subnetting
* VLAN configuration
* OSPF
* STP
* DHCP
* DNS
* NAT

---

This project was developed as part of the ITCE400 course project.
