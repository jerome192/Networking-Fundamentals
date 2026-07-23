# Technical Investigation Report
# Technical Investigation Report

## Phase 1: Windows Server 2025 Network Configuration

### Objective

The first stage of this project involved configuring the Windows Server 2025 virtual machine with a static IPv4 address on the isolated VirtualBox internal network named `intnet`.

A static IPv4 address was selected because the server will later provide network services to other systems within the laboratory network. A predictable address is therefore necessary so that client systems can reliably locate the server.

---

### Initial Network State

Before the static configuration was applied, the Windows Server 2025 network adapter was configured to obtain an IPv4 address automatically through DHCP.

However, the `intnet` network did not yet have an operational DHCP server. Consequently, the server was unable to obtain a normal IPv4 address from a DHCP service.

Windows automatically assigned the adapter an address from the Automatic Private IP Addressing (APIPA) range:

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

An address in the `169.254.0.0/16` range indicates that the host was unable to obtain an IPv4 address from a DHCP server and automatically assigned itself an address for limited local communication.

At this stage, the isolated internal network did not have an operational IPv4 DHCP service.

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

The resulting configuration was verified using:

```cmd
ipconfig /all
```

The verification output is shown below.

![Windows Server IP Configuration](evidence/01-server-ipconfig-all.png)

The configuration confirms that:

* DHCP is disabled.
* The server has the static IPv4 address `192.168.100.10`.
* The subnet mask is `255.255.255.0`.
* No default gateway is currently configured.
* The server is configured to use `192.168.100.10` as its DNS server.

---

### Reason for Using a Static IP Address

The server is intended to provide network services to other systems within the laboratory network.

A dynamically changing address would make it difficult for client systems to reliably locate the server. Assigning a static address therefore establishes a predictable endpoint for future services.

The current logical configuration is:

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

At the end of this phase, the Windows Server 2025 virtual machine has been configured with a static IPv4 address on the isolated `intnet` network.

```text
IPv4 Address: 192.168.100.10
Subnet Mask: 255.255.255.0
DHCP: Disabled
Default Gateway: None
DNS Server: 192.168.100.10
```

This configuration establishes the server as a predictable host on the laboratory network.

The next phase will involve configuring the Kali Linux interface connected to `intnet` with a temporary static IPv4 address in the same subnet. This will allow connectivity and ARP resolution to be tested before DHCP services are introduced.
