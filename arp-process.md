# ARP Process (Address Resolution Protocol)

## Introduction

The Address Resolution Protocol (ARP) is used to map an IPv4 address to a MAC address within a local network.

Devices use ARP because communication on a LAN happens using MAC addresses at Layer 2, while IP addresses operate at Layer 3.

Without ARP, a device would know the destination IP but would not know where to send the Ethernet frame.

ARP is essential for local communication and for sending traffic to the default gateway.

---

## What ARP Does

ARP answers one important question:

```text
Who has this IP address?
```

It allows a host to discover the MAC address associated with an IPv4 address.

Example:

```text
IP Address: 192.168.1.1
MAC Address: AA:BB:CC:DD:EE:FF
```

This mapping allows frames to be delivered correctly.

---

## Why ARP is Needed

Suppose a host wants to send data.

The host knows:

- Its own IP address
- Its own MAC address
- The destination IP address

But Ethernet requires:

- Destination MAC address

This is where ARP becomes necessary.

Without ARP:

```text
IP known
MAC unknown
Communication fails
```

---

## ARP Process Overview

The ARP process follows these steps:

1. Host checks ARP cache
2. If no entry exists, it sends an ARP request
3. The target device replies
4. The host stores the mapping
5. Communication begins

---

## Diagram: ARP Request and Reply

![ARP Process](images/arp-process.gif)

---

## Step 1: ARP Cache Check

Before sending an ARP request, the host checks its ARP cache.

This is a temporary table storing:

```text
IP → MAC
```

Example:

```text
192.168.1.1 → AA:BB:CC:DD:EE:FF
```

If the entry exists, ARP is skipped.

This improves efficiency.

---

## Step 2: ARP Request

If the MAC address is unknown, the host sends a broadcast request.

Example:

```text
Who has 192.168.1.1? Tell 192.168.1.10
```

Important:

- Source MAC = sender MAC
- Destination MAC = FF:FF:FF:FF:FF:FF (broadcast)

This means all devices on the LAN receive it.

---

## Step 3: ARP Reply

The device with the matching IP responds.

Example:

```text
192.168.1.1 is at AA:BB:CC:DD:EE:FF
```

This reply is unicast directly to the requesting host.

Now the sender knows the correct MAC address.

---

## Step 4: Store in ARP Cache

The host stores the new mapping.

Example:

```text
192.168.1.1 → AA:BB:CC:DD:EE:FF
```

This avoids repeated ARP requests.

Entries eventually expire.

---

## ARP and the Default Gateway

ARP is very important when sending traffic outside the LAN.

Example:

Host wants to reach:

```text
142.250.190.78
```

This is not local.

The host does NOT ARP for:

```text
142.250.190.78
```

Instead it ARPs for:

```text
Default Gateway IP
```

Important rule:

ARP resolves the **next-hop MAC**, not the final destination MAC.

This is one of the most important networking concepts.

---

## Security Relevance

ARP is heavily used in network attacks.

Examples:

- ARP spoofing
- Man-in-the-middle (MITM)
- Traffic interception
- Session hijacking

Attackers can send fake ARP replies to poison the ARP cache.

Example:

```text
Gateway IP → Attacker MAC
```

This redirects traffic through the attacker.

This makes ARP important in penetration testing.

---

## Key Takeaways

- ARP maps IPv4 addresses to MAC addresses.
- ARP operates only within local networks.
- ARP uses broadcasts for requests.
- ARP uses unicast for replies.
- ARP caches improve efficiency.
- ARP resolves the next hop, not the final destination.

---

## Conclusion

ARP is one of the most fundamental protocols in networking because it bridges Layer 3 addressing and Layer 2 delivery.

Without ARP, local communication would not function.

For penetration testers, understanding ARP is important because it reveals how local traffic flows and how attackers can manipulate that flow.
