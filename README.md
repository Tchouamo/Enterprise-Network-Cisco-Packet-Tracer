# Departmental Office LAN Design: IP Addressing, Segmentation, and Secure Remote Access (Cisco Packet Tracer)

## Project Overview

This repository presents a detailed departmental Local Area Network (LAN) design, built and simulated using **Cisco Packet Tracer**. The project focuses on creating a segmented network for an office with distinct departments (e.g., Accounting, Delivery), emphasizing structured IP addressing, inter-departmental routing, and secure remote management.

Key aspects of this project include:

* **Departmental Segmentation:** Designing separate logical networks for different departments using distinct IP subnets for enhanced organization and security.
* **Comprehensive IP Addressing:** Explicitly assigning and documenting static IP addresses, subnet masks, and default gateways for every device (PCs, Printers, Router interfaces).
* **Router-Based Inter-Departmental Routing:** Configuring a central router to enable seamless and efficient communication between the segmented departments.
* **Secure Remote Management (SSH):** Implementing and verifying Secure Shell (SSH) for encrypted command-line access to the router, demonstrating best practices for network device administration with a 1024-bit RSA key and custom domain.
* **Basic Remote Management (Telnet):** Configuring Telnet access for basic, unencrypted remote command-line management of the router (primarily for demonstration/comparison purposes).
* **Device Integration:** Incorporating various end devices, including PCs and network printers, within their respective departmental segments.
* **Clear Documentation:** Visualizing the network structure with clear labels for departments, IP schemes, and device roles within the Packet Tracer environment.

This project demonstrates practical skills in network planning, precise IP addressing, the implementation of departmental network segregation, and the configuration of essential remote access protocols.

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

## Configuration Highlights

### Router Remote Access Configuration (Partial Example)

```cli
! Global configuration for SSH
hostname Router
ip domain name mydomain.com
crypto key generate rsa modulus 1024
username admin password Zxcvb1
!
! VTY line configuration for remote access
line vty 0 4
 password Zxcvb12  ! Password for Telnet access
 login local       ! Use local username database (for SSH and fallback for Telnet if transport input all)
 transport input ssh telnet ! Allows both SSH and Telnet connections
!
! Interface configurations (as described in Network Topology section)
interface GigabitEthernet0/0
 ip address 192.168.40.1 255.255.255.128
 no shutdown
interface GigabitEthernet0/1
 ip address 192.168.40.129 255.255.255.128
 no shutdown
