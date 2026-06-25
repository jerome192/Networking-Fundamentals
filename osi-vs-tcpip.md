# OSI vs TCP/IP Models

## Introduction

Network communication follows structured models that define how data is transmitted between devices. These models divide communication into layers, where each layer performs a specific function.

The two most important models in networking are:

* **OSI (Open Systems Interconnection) Model**
* **TCP/IP (Transmission Control Protocol / Internet Protocol) Model**

Understanding these models is fundamental because all network communication, packet transmission, and protocol interactions follow them. In cybersecurity and penetration testing, these models help identify where attacks occur and where traffic can be analyzed.

---

## The OSI Model

The OSI model is a conceptual framework that divides network communication into seven layers.

### OSI Layers

| Layer | Name         | Function                          |
| ----- | ------------ | --------------------------------- |
| 7     | Application  | Provides services to end users    |
| 6     | Presentation | Data formatting and encryption    |
| 5     | Session      | Manages communication sessions    |
| 4     | Transport    | Reliable end-to-end communication |
| 3     | Network      | Logical addressing and routing    |
| 2     | Data Link    | MAC addressing and frame delivery |
| 1     | Physical     | Transmission of raw bits          |

The OSI model is mainly used for understanding, troubleshooting, and analyzing network communication.

---

## The TCP/IP Model

The TCP/IP model is the practical model used in modern internet communication.

It consists of four layers:

| Layer          | Function                                 |
| -------------- | ---------------------------------------- |
| Application    | User interaction and data formatting     |
| Transport      | End-to-end communication                 |
| Internet       | IP addressing and routing                |
| Network Access | Physical transmission and MAC addressing |

Unlike the OSI model, TCP/IP combines multiple OSI layers into fewer practical layers.

---

## Mapping OSI to TCP/IP

The TCP/IP model simplifies the OSI model by combining some layers.

| OSI Model    | TCP/IP Model   |
| ------------ | -------------- |
| Application  | Application    |
| Presentation | Application    |
| Session      | Application    |
| Transport    | Transport      |
| Network      | Internet       |
| Data Link    | Network Access |
| Physical     | Network Access |

This mapping helps explain how theoretical networking models are implemented in real-world communication.

---

## Encapsulation Process

When data is sent from one host to another:

1. The Application layer generates the data.
2. Each lower layer adds its own header.
3. The data is transmitted across the network.
4. The receiving host removes each header in reverse order.

This process is called:

* **Encapsulation** (sending)
* **De-encapsulation** (receiving)

---

## Diagram: OSI and TCP/IP Mapping

![OSI vs TCP/IP Model](images/osi-vs-tcpip.png)

---

## Practical Example: Accessing a Website

When a user visits a website:

* The **Application layer** handles HTTP/HTTPS.
* The **Transport layer** handles TCP.
* The **Internet layer** handles IP.
* The **Network Access layer** handles Ethernet and ARP.

For example:

A browser sends an HTTP request, which is encapsulated into TCP, then IP, then Ethernet, before being transmitted to the router and across the internet.

This demonstrates how multiple protocols work together across different layers.

---

## Security Relevance

Understanding these models is critical in penetration testing.

Examples:

* **Application Layer** → Web attacks (XSS, SQL Injection)
* **Transport Layer** → Port scanning
* **Network Layer** → IP spoofing
* **Data Link Layer** → ARP spoofing
* **Physical Layer** → Hardware tapping

This helps security professionals identify where attacks occur and how defenses are applied.

---

## Key Takeaways

* The OSI model has **7 layers** and is conceptual.
* The TCP/IP model has **4 layers** and is practical.
* Both models explain how devices communicate.
* Encapsulation allows data to move across networks.
* Understanding these models is essential for networking and cybersecurity.

---

## Conclusion

The OSI and TCP/IP models form the foundation of all network communication. They provide a structured method for understanding how protocols interact and how data moves across systems.

For cybersecurity professionals and penetration testers, these models are essential because they reveal where vulnerabilities exist and how attacks can be analyzed at different layers.
