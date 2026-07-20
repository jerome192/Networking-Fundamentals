# Technical Investigation Report

## Phase 1: Configuring the Windows Server 2025 Network Interface

### Objective

The Windows Server 2025 virtual machine was configured with a static IPv4 address on the isolated VirtualBox internal network named `intnet`.

A static IPv4 address was assigned because the server will later provide network services to other devices within the laboratory network. A predictable address is therefore required so that client systems can reliably locate the server.

---

### Initial Network State

Before configuration, the Windows Server 2025 network adapter was configured to obtain an IPv4 address automatically through DHCP.

However, no DHCP server was currently available on the isolated `intnet` network. Consequently, the server was unable to obtain an IPv4 address through DHCP.

Windows therefore automatically assigned the adapter an address from the Automatic Private IP Addressing (APIPA) range:

```text
IPv4 Address: 169.254.74.241
Subnet Mask: 255.255.0.0
```

The relevant initial configuration was:

```text
DHCP Enabled: Yes
IPv4 Address: 169.254.74.241
Default Gateway: None
```

An address in the `169.254.0.0/16` range indicates that the host was unable to obtain an IPv4 address from a DHCP server and automatically self-assigned an address for limited local communication.

At this stage, the internal network was therefore an isolated network without an operational IPv4 DHCP service.

---

### Static IPv4 Configuration

The Windows Server 2025 network interface was subsequently configured with a static IPv4 address:

```text
IPv4 Address: 192.168.100.10
Subnet Mask: 255.255.255.0
Default Gateway: None
DNS Server: 192.168.100.10
```

This places the server on the following IPv4 network:

```text
Network: 192.168.100.0/24
Server:  192.168.100.10/24
```

The configuration was verified using:

```cmd
ipconfig /all
```

The resulting configuration confirmed:

```text
DHCP Enabled: No
IPv4 Address: 192.168.100.10
Subnet Mask: 255.255.255.0
Default Gateway: None
DNS Server: 192.168.100.10
```

---

### Reason for Using a Static IP Address

The server is intended to provide network services to other systems within the laboratory network.

A dynamically changing address would make it difficult for client systems to reliably locate the server. Assigning a static address therefore establishes a predictable endpoint for future services.

The current configuration is:

```text
Windows Server 2025
        │
        │ 192.168.100.10/24
        │
        ▼
Internal Network: intnet
```

---

### Current State

At the end of this phase, the Windows Server 2025 virtual machine has been successfully configured with a static IPv4 address on the isolated `intnet` network.

```text
IPv4 Address: 192.168.100.10
Subnet Mask: 255.255.255.0
DHCP: Disabled
Default Gateway: None
DNS Server: 192.168.100.10
```

The next phase will configure the Kali Linux interface connected to `intnet` with a temporary static IPv4 address in the same subnet. This will allow connectivity and ARP resolution to be tested before DHCP services are introduced.
