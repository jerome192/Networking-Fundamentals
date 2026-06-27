# IPv4 Addressing and Subnetting

## Introduction

IPv4 addressing is one of the most fundamental concepts in networking. Every device on a network requires an IP address to communicate.

Subnetting is the process of dividing a larger network into smaller logical networks. This improves organization, efficiency, and security.

In cybersecurity and penetration testing, understanding IP addressing and subnetting is important because it helps identify network boundaries, scope targets, and understand how internal systems are segmented.

---

## What is IPv4?

IPv4 (Internet Protocol Version 4) is a Layer 3 protocol used for logical addressing.

An IPv4 address consists of **32 bits**, divided into **4 octets**.

Example:

```text
192.168.1.10
```

Each octet ranges from:

```text
0 - 255
```

Example binary:

```text
192.168.1.10
11000000.10101000.00000001.00001010
```

This binary structure is what routers use for addressing decisions.

---

## Structure of an IPv4 Address

An IPv4 address consists of two parts:

- **Network Portion**
- **Host Portion**

Example:

```text
192.168.1.10/24
```

This means:

```text
Network = 192.168.1
Host = .10
```

The subnet mask determines where the split occurs.

---

## Subnet Mask

A subnet mask identifies which part of the IP address belongs to the network.

Example:

```text
255.255.255.0
```

Binary:

```text
11111111.11111111.11111111.00000000
```

This means:

- first 24 bits = network
- last 8 bits = hosts

CIDR notation:

```text
/24
```

---

## Why Subnetting is Needed

Without subnetting:

- networks become too large
- broadcasts increase
- management becomes difficult

Subnetting helps:

- reduce broadcast domains
- improve security segmentation
- organize departments or systems
- control network scope

This is important in enterprise and internal pentesting.

---

## Example of Subnetting

Original network:

```text
192.168.1.0/24
```

This provides:

```text
256 addresses
254 usable hosts
```

If divided into four subnets:

```text
192.168.1.0/26
192.168.1.64/26
192.168.1.128/26
192.168.1.192/26
```

Each subnet now provides:

```text
64 addresses
62 usable hosts
```

---

## Diagram: Subnet Division

![IPv4 Subnetting](images/ipv4-subnetting)

---

## Network, Broadcast, and Host Range

Example:

```text
192.168.1.0/26
```

Results:

| Type | Value |
|---|---|
| Network Address | 192.168.1.0 |
| First Host | 192.168.1.1 |
| Last Host | 192.168.1.62 |
| Broadcast Address | 192.168.1.63 |

Important:

- first address = network ID
- last address = broadcast
- usable hosts are in between

This is critical for scanning and enumeration.

---

## Security Relevance

Subnetting is important in penetration testing because it helps identify:

- target scope
- segmented departments
- internal VLAN boundaries
- possible lateral movement paths

Example:

A pentester may scan:

```text
192.168.10.0/24
```

instead of the whole:

```text
192.168.0.0/16
```

This makes testing more efficient.

---

## Key Takeaways

- IPv4 uses 32-bit logical addressing.
- Subnet masks divide network and host portions.
- Subnetting creates smaller logical networks.
- Each subnet has network and broadcast addresses.
- Subnetting improves organization and security.

---

## Conclusion

IPv4 addressing and subnetting form the basis of network organization and communication.

For penetration testers, understanding subnetting is essential because it defines target boundaries, affects enumeration, and reveals how internal networks are structured.
