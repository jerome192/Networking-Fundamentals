# Build and Analyze a Small Virtual Network

## Overview

This project documents the design, implementation, and analysis of a small virtual network built using Oracle VirtualBox. The objective is to gain practical experience with fundamental networking concepts by configuring and testing a realistic laboratory environment rather than relying solely on theoretical study.

The laboratory consists of multiple virtual machines connected through different VirtualBox network modes, allowing network communication to be observed, tested, and analysed in a controlled environment.

---

## Objectives

The project aims to:

* Build an isolated virtual network using Oracle VirtualBox.
* Configure a Windows Server 2025 machine as the central network server.
* Configure Linux and Windows client machines.
* Understand static and dynamic IPv4 addressing.
* Investigate Address Resolution Protocol (ARP).
* Configure and analyse DHCP.
* Configure and test DNS.
* Examine routing and VirtualBox network adapters.
* Capture and analyse network traffic using Wireshark.
* Document every stage with commands, screenshots, and technical explanations.

---

## Laboratory Environment

### Host Machine

* Windows 11

### Virtual Machines

* Kali Linux
* Windows Server 2025
* Windows 11

### VirtualBox Network Modes

* NAT
* Internal Network (`intnet`)
* Host-Only Adapter

---

## Skills Demonstrated

This project demonstrates practical understanding of:

* IPv4 addressing
* Static IP configuration
* DHCP
* DNS
* ARP
* Routing fundamentals
* Network troubleshooting
* Packet analysis
* Windows Server administration
* Linux networking
* VirtualBox networking

---

## Repository Structure

```text
01-build-and-analyze-a-small-network/
│
├── README.md
├── report.md
├── evidence/
└── topology/
```

* **README.md** – Project overview and objectives.
* **report.md** – Detailed technical investigation and configuration process.
* **evidence/** – Screenshots and command outputs collected during the project.
* **topology/** – Network diagrams illustrating the laboratory environment.

---

## Project Progress

| Phase                                | Status        |
| ------------------------------------ | ------------- |
| Windows Server Network Configuration | ✅ Completed   |
| Client Configuration                 | ⏳ In Progress |
| Connectivity Testing                 | ⏳ Pending     |
| ARP Investigation                    | ⏳ Pending     |
| DHCP Configuration                   | ⏳ Pending     |
| DNS Configuration                    | ⏳ Pending     |
| Routing Analysis                     | ⏳ Pending     |
| Packet Capture Analysis              | ⏳ Pending     |
| Final Documentation                  | ⏳ Pending     |

---

## Learning Outcomes

By completing this project, I aim to strengthen my understanding of computer networking through practical implementation. Rather than simply learning networking concepts theoretically, this project focuses on configuring, testing, analysing, troubleshooting, and documenting a complete virtual network using industry-standard tools and operating systems.

The knowledge and experience gained from this project will provide a strong foundation for future studies in Linux, Windows administration, web application security, penetration testing, and cybersecurity.
