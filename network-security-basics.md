# Network Security Basics

## Introduction

Network security is the practice of protecting systems, devices, and data from unauthorized access, attacks, and misuse.

As networks connect users, applications, and services, they also create attack surfaces.

This makes security an essential part of networking.

In penetration testing, understanding network security is important because attackers often exploit weak configurations, exposed services, and poor security controls.

---

## Why Network Security Matters

Modern networks carry sensitive data.

Examples:

- login credentials
- emails
- financial transactions
- internal communications

Without security:

- attackers can intercept traffic
- systems can be compromised
- services can be disrupted

Network security protects:

```text
Confidentiality
Integrity
Availability
```

This is known as the:

```text
CIA Triad
```

These are the three core goals of security.

---

## Common Security Devices

### Firewall

A firewall filters traffic based on security rules.

Example:

```text
Allow Port 443
Block Port 23
```

Purpose:

- control access
- block unwanted traffic

Firewalls reduce attack surfaces.

---

### IDS (Intrusion Detection System)

An IDS monitors traffic for suspicious behavior.

Examples:

- port scans
- brute force attempts
- malware activity

It detects threats and alerts administrators.

---

### IPS (Intrusion Prevention System)

An IPS detects threats and actively blocks them.

Unlike IDS:

it can stop malicious traffic automatically.

---

### VPN (Virtual Private Network)

A VPN encrypts communication over public or untrusted networks.

Purpose:

- protect remote communication
- maintain confidentiality

VPNs secure data in transit.

---

## Common Network Threats

### Man-in-the-Middle (MITM)

An attacker intercepts communication between two systems.

Examples:

- ARP spoofing
- rogue gateways

This can expose sensitive information.

---

### DNS Spoofing

An attacker sends fake DNS responses.

This can redirect users to malicious websites.

---

### Packet Sniffing

Attackers capture network traffic.

If communication is unencrypted:

sensitive information can be exposed.

---

### Port Scanning

Attackers identify open services.

This helps map the attack surface.

---

### Denial of Service (DoS)

Attackers overwhelm a system and make services unavailable.

This affects availability.

---

## Access Control

Access control limits who can use resources.

Examples:

- usernames and passwords
- ACLs (Access Control Lists)
- multi-factor authentication

This reduces unauthorized access.

---

## Encryption

Encryption protects data during transmission.

Examples:

```text
HTTPS
SSH
VPN
```

This prevents attackers from reading intercepted traffic.

Without encryption:

packet sniffing becomes dangerous.

---

## Principle of Least Privilege

Users should only have the minimum permissions required.

This reduces risk if an account is compromised.

This is a core security principle.

---

## Security Relevance in Penetration Testing

Understanding network security helps penetration testers:

- identify weak firewall rules
- find exposed services
- test access controls
- analyze insecure protocols
- understand trust relationships

Many successful attacks rely on weak security controls rather than protocol weaknesses.

---

## Key Takeaways

- Network security protects systems and data.
- Firewalls control traffic.
- IDS detects threats.
- IPS prevents attacks.
- Encryption secures communication.
- Weak configurations create vulnerabilities.

---

## Conclusion

Network security is a fundamental part of networking because every connected system can become a target.

For penetration testers, understanding security controls is important because it helps identify weaknesses, understand defenses, and analyze attack paths effectively.
