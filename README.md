# Departmental Office LAN Design: IP Addressing & Segmentation (Cisco Packet Tracer)

## Project Overview

This repository presents a detailed departmental Local Area Network (LAN) design, built and simulated using **Cisco Packet Tracer**. The project focuses on creating a segmented network for an office with distinct departments (e.g., Accounting, Delivery), emphasizing structured IP addressing and inter-departmental routing.

Key aspects of this project include:

* **Departmental Segmentation:** Designing separate logical networks for different departments using distinct IP subnets.
* **Comprehensive IP Addressing:** Explicitly assigning and documenting static IP addresses, subnet masks, and default gateways for every device (PCs, Printers, Router interfaces).
* **Router-Based Inter-Departmental Routing:** Configuring a central router to enable seamless communication between the segmented departments.
* **Device Integration:** Incorporating various end devices, including PCs and network printers, within their respective departmental segments.
* **Clear Documentation:** Visualizing the network structure with clear labels for departments, IP schemes, and device roles.

This project demonstrates practical skills in network planning, precise IP addressing, and the implementation of departmental network segregation.

## Network Topology & IP Scheme

The network features a central router acting as the backbone for communication between two primary departments: "ACCOUNTING DEPARTMENT" and "DELIVERY DEPARTMENT."

* **Router (1941):** Routes traffic between the 192.168.40.0/25 and 192.168.40.128/25 subnets.
    * **GigabitEthernet0/0:** 192.168.40.1/25
    * **GigabitEthernet0/1:** 192.168.40.129/25
* **Switches (2960-24TT):** Dedicated to each department.
* **End Devices (PCs & Printers):** Statically configured within their respective departmental subnets.

### Accounting Department (192.168.40.0/25)
* **Network Address:** 192.168.40.0
* **Broadcast Address:** 192.168.40.127
* **Gateway:** 192.168.40.1
* **Devices:**
    * PC0: 192.168.40.2
    * PC1: 192.168.40.3
    * Printer0: 192.168.40.4

### Delivery Department (192.168.40.128/25)
* **Network Address:** 192.168.40.128
* **Broadcast Address:** 192.168.40.255
* **Gateway:** 192.168.40.129
* **Devices:**
    * Printer1: 192.168.40.130
    * PC-PT: 192.168.40.131
    * PC-PT: 192.168.40.132

## Files in this Repository

* `departmental_office_LAN.pkt`: The Cisco Packet Tracer file with the full network design and configurations.
* `network.png`: A detailed screenshot of the network topology with IP addressing information.

## How to Use

1.  Download and install **Cisco Packet Tracer** (version 8.2.2 or higher recommended).
2.  Clone this repository: `git clone [YourRepoURL]`
3.  Open `departmental_office_LAN.pkt` in Cisco Packet Tracer.
4.  Explore the configurations and verify inter-departmental communication.

---
