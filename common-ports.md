# Common Ports and Services

## Introduction

Ports are logical communication endpoints used by transport-layer protocols such as TCP and UDP.

They allow multiple services to run on the same system while keeping traffic organized.

When a device communicates over a network, the destination port tells the system which service should process the incoming data.

In penetration testing, understanding ports is critical because identifying open ports reveals potential attack surfaces.

---

## What is a Port?

A port is a numbered endpoint associated with a network service.

Example:

```text
192.168.1.10:80
```

This means:

- IP address:

```text
192.168.1.10
```

- Port:

```text
80
```

The IP identifies the host.

The port identifies the service.

---

## Port Ranges

Ports are divided into three main ranges.

### Well-Known Ports

```text
0 – 1023
```

Reserved for common services.

Examples:

- 80 (HTTP)
- 443 (HTTPS)
- 22 (SSH)

---

### Registered Ports

```text
1024 – 49151
```

Used by applications and services.

Examples:

- 3306 (MySQL)
- 5432 (PostgreSQL)

---

### Dynamic / Ephemeral Ports

```text
49152 – 65535
```

Temporary ports used for client-side communication.

Example:

A browser may use:

```text
52341
```

to communicate with a web server.

---

## Common Ports Table

| Port | Protocol | Service |
|---|---|---|
| 20/21 | TCP | FTP |
| 22 | TCP | SSH |
| 23 | TCP | Telnet |
| 25 | TCP | SMTP |
| 53 | TCP/UDP | DNS |
| 67/68 | UDP | DHCP |
| 69 | UDP | TFTP |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 |
| 143 | TCP | IMAP |
| 161 | UDP | SNMP |
| 443 | TCP | HTTPS |
| 445 | TCP | SMB |
| 3389 | TCP | RDP |

These are some of the most commonly encountered ports during penetration testing.

---

## Why Ports Matter

Open ports indicate running services.

Example:

```text
Port 22 open → SSH service running
```

This gives attackers information about:

- available services
- possible vulnerabilities
- attack vectors

Port enumeration is one of the first steps in reconnaissance.

---

## Port Scanning

Port scanning is used to identify open ports.

Common tool:

```text
nmap
```

Example:

```bash
nmap 192.168.1.10
```

This reveals:

- open ports
- service versions
- operating system hints

Port scanning is essential in pentesting.

---

## Common Attack Surfaces by Port

Examples:

### Port 22 (SSH)

Possible attacks:

- brute force
- weak credentials

---

### Port 80/443 (HTTP/HTTPS)

Possible attacks:

- SQL injection
- XSS
- directory enumeration

---

### Port 445 (SMB)

Possible attacks:

- null sessions
- EternalBlue
- file enumeration

---

### Port 3389 (RDP)

Possible attacks:

- credential attacks
- weak configurations

---

## Security Relevance

Ports directly define the attack surface.

Understanding them helps with:

- enumeration
- vulnerability discovery
- exploitation planning
- service identification

Most penetration tests begin by identifying open ports.

---

## Key Takeaways

- Ports identify services on a host.
- IP identifies the system.
- Port identifies the application.
- Open ports reveal attack surfaces.
- Port scanning is essential for reconnaissance.

---

## Conclusion

Ports are one of the most important parts of networking because they connect services to communication channels.

For penetration testers, understanding common ports is critical because they reveal how systems communicate and where vulnerabilities may exist.
