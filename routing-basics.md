# Routing Basics

## Introduction

Routing is the process of forwarding packets from one network to another.

When a device wants to communicate outside its local network, the packet must be sent to a router, which decides the best path toward the destination.

Routing is one of the most important concepts in networking because it connects different networks together and allows communication across the internet.

For penetration testers, understanding routing helps explain packet paths, pivoting, and lateral movement.

---

## What is Routing?

Routing is the process of examining a packet’s destination IP address and forwarding it toward the correct network.

Routers operate at:

```text
Layer 3 (Network Layer)
```

Routers make forwarding decisions using:

- Destination IP address
- Routing table

Example:

```text
Destination: 8.8.8.8
```

The router checks its routing table and selects the next hop.

---

## Why Routing is Needed

Devices can only directly communicate within their own local subnet.

Example:

```text
Host A: 192.168.1.10/24
Host B: 192.168.2.10/24
```

These are different networks.

Direct communication is not possible.

A router is required.

Without routing:

```text
Remote communication fails
```

---

## How Routing Works

The routing process:

1. Host determines destination is remote.
2. Host forwards packet to default gateway.
3. Router checks destination IP.
4. Router matches route in routing table.
5. Router forwards packet to next hop.
6. Process repeats until destination is reached.

This allows packets to travel across multiple networks.

---

## Routing Table

A routing table stores known network paths.

Example:

```text
Destination Network    Next Hop
192.168.1.0/24         Local
192.168.2.0/24         10.0.0.2
0.0.0.0/0              ISP Gateway
```

Important:

The router uses the **most specific match**.

This is called:

```text
Longest Prefix Match
```

---

## Default Route

A default route is used when no specific route exists.

Example:

```text
0.0.0.0/0
```

This means:

```text
Send all unknown traffic here
```

Usually this points to the ISP.

This is what allows internet access.

Without a default route:

External communication fails.

---

## Example: Accessing a Website

Host:

```text
192.168.1.10
```

Destination:

```text
142.250.190.78
```

Process:

- Host checks subnet
- Destination is remote
- Packet sent to default gateway
- Router checks routing table
- Router forwards packet toward the internet

This continues until the packet reaches the web server.

---

## Static vs Dynamic Routing

### Static Routing

Manually configured.

Example:

```text
ip route 192.168.2.0 255.255.255.0 10.0.0.2
```

Advantages:

- Simple
- Predictable

Disadvantages:

- Hard to scale

---

### Dynamic Routing

Routes are learned automatically.

Examples:

- OSPF
- EIGRP
- BGP

Advantages:

- Scalable
- Adaptive

Disadvantages:

- More complex

---

## Security Relevance

Routing is important in penetration testing.

Examples:

- Understanding pivot paths
- Internal segmentation
- Route-based restrictions
- Traffic redirection
- Lateral movement

Attackers often rely on routing knowledge to move between internal networks.

---

## Key Takeaways

- Routing forwards packets between networks.
- Routers use routing tables for decisions.
- Default routes handle unknown destinations.
- Static routes are manual.
- Dynamic routes are learned automatically.
- Routing enables internet communication.

---

## Conclusion

Routing is the mechanism that connects networks together and allows data to move beyond local boundaries.

For penetration testers, understanding routing is essential because it reveals how traffic travels, how networks are connected, and how movement between systems is possible.
