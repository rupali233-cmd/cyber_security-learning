
# Networking Basics

## ARP (Address Resolution Protocol)

**Meaning:** Finds the MAC Address when the IP Address is known.

**Layer:** Data Link Layer

**Port:** No Port

**Work:**
- Maps IP Address to MAC Address.
- Used only in a Local Area Network (LAN).

**Command:**
```
arp -a
```

---

## HTTP (HyperText Transfer Protocol)

**Meaning:** Transfers web pages between a browser and a web server.

**Layer:** Application Layer

**Port:** 80

**Work:**
- Used for web browsing.
- Transfers data in plain text.
- Not secure.

---

## HTTPS (HyperText Transfer Protocol Secure)

**Meaning:** Secure version of HTTP.

**Layer:** Application Layer

**Port:** 443

**Work:**
- Encrypts communication using SSL/TLS.
- Protects sensitive information.
- Used for secure websites.

---

## TCP (Transmission Control Protocol)

**Meaning:** Reliable communication protocol.

**Layer:** Transport Layer

**Port:** No Fixed Port

**Work:**
- Connection-oriented.
- Reliable data transfer.
- Uses Three-Way Handshake.
- Ensures packets are delivered in order.

**Common Services Using TCP:**
- HTTP (80)
- HTTPS (443)
- FTP (21)
- SSH (22)
- SMTP (25)

---

## UDP (User Datagram Protocol)

**Meaning:** Fast communication protocol.

**Layer:** Transport Layer

**Port:** No Fixed Port

**Work:**
- Connectionless.
- Faster than TCP.
- No guarantee of packet delivery.
- Used where speed is more important than reliability.

**Common Services Using UDP:**
- DNS (53)
- DHCP (67/68)
- TFTP (69)
- SNMP (161)

---
# Networking Basics: ICMP, DHCP, and DNS

## 1. ICMP (Internet Control Message Protocol)

### What is ICMP?
ICMP is a Layer 3 (Network Layer) protocol used for error reporting, diagnostics, and network troubleshooting. It does not transport application data like TCP or UDP.

### Purpose
- Reports network errors
- Tests network connectivity
- Measures latency
- Detects unreachable hosts or networks

### Common ICMP Message Types

| Type | Description |
|------|-------------|
| Echo Request | Sent by `ping` to check connectivity |
| Echo Reply | Response to an Echo Request |
| Destination Unreachable | Destination cannot be reached |
| Time Exceeded | Packet's TTL reached zero |
| Redirect | Suggests a better route |
| Parameter Problem | Header contains an error |

### ICMP in Action

When you run:

```bash
ping google.com
```

The computer sends an **ICMP Echo Request**.

If Google responds, it sends an **ICMP Echo Reply**.

Example:

```
PC → Echo Request → Server
PC ← Echo Reply ← Server
```

### TTL (Time To Live)

TTL limits how long a packet can travel.

- Router decreases TTL by 1
- When TTL becomes 0
- Router discards the packet
- Sends ICMP Time Exceeded message

Used by:

```bash
traceroute
```

or

```bash
tracert
```

### Advantages

- Network diagnostics
- Detect unreachable devices
- Helps troubleshoot routing problems

### Limitations

- No encryption
- Can be abused for reconnaissance
- Often blocked by firewalls

---

# 2. DHCP (Dynamic Host Configuration Protocol)

## What is DHCP?

DHCP automatically assigns network configuration to devices joining a network.

Instead of manually assigning IP addresses, DHCP performs the configuration automatically.

### Information Assigned by DHCP

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server
- Lease Time

### DHCP Ports

| Device | Port |
|---------|------|
| Client | UDP 68 |
| Server | UDP 67 |

---

## DHCP Process (DORA)

### D - Discover

Client broadcasts:

> "Is there any DHCP server available?"

---

### O - Offer

DHCP server replies:

> "I can offer you this IP address."

---

### R - Request

Client responds:

> "I want this offered IP."

---

### A - Acknowledge

Server confirms:

> "IP assigned successfully."

The client can now communicate on the network.

### DHCP Flow

```
Client
   │
   │ DHCP Discover
   ▼
DHCP Server
   │
   │ DHCP Offer
   ▼
Client
   │
   │ DHCP Request
   ▼
DHCP Server
   │
   │ DHCP ACK
   ▼
Client receives IP Address
```

---

## DHCP Lease

The assigned IP address is temporary.

The client must renew it before the lease expires.

If not renewed:

- IP becomes available
- Another device may receive it

---

## Advantages

- Automatic IP allocation
- Prevents IP conflicts
- Easy network management
- Saves administrator time

---

## Disadvantages

- Single point of failure if no backup DHCP server exists
- Rogue DHCP servers can assign incorrect settings

---

# 3. DNS (Domain Name System)

## What is DNS?

DNS converts human-readable domain names into IP addresses.

Example:

```
google.com
        ↓
142.250.183.14
```

Humans remember names.

Computers communicate using IP addresses.

---

## Why DNS is Needed

Without DNS:

```
https://142.250.183.14
```

Instead of

```
https://google.com
```

DNS makes the Internet easier to use.

---

## DNS Port

| Protocol | Port |
|-----------|------|
| UDP | 53 |
| TCP | 53 |

UDP is used for most queries.

TCP is used for:

- Zone transfers
- Large responses
- DNSSEC

---

## DNS Resolution Process

Suppose a user enters:

```
www.example.com
```

The process is:

```
User
   │
   ▼
Browser
   │
   ▼
Local DNS Resolver
   │
   ▼
Root DNS Server
   │
   ▼
TLD Server (.com)
   │
   ▼
Authoritative DNS Server
   │
   ▼
Returns IP Address
   │
   ▼
Browser connects to website
```

---

## Types of DNS Records

### A Record

Maps a domain to an IPv4 address.

Example:

```
example.com → 93.184.216.34
```

---

### AAAA Record

Maps a domain to an IPv6 address.

---

### CNAME Record

Creates an alias.

Example:

```
www.example.com
        ↓
example.com
```

---

### MX Record

Specifies the mail server.

Example:

```
gmail.com → Mail Server
```

---

### NS Record

Specifies the authoritative name server.

---

### TXT Record

Stores text information.

Often used for:

- SPF
- DKIM
- Domain verification

---

### PTR Record

Reverse DNS lookup.

IP Address

↓

Domain Name

---

## DNS Caching

DNS responses are stored temporarily.

Benefits:

- Faster browsing
- Less DNS traffic
- Reduced latency

---

## Common DNS Attacks

### DNS Spoofing

Attacker provides a fake DNS response.

Victim is redirected to a malicious website.

---

### DNS Cache Poisoning

Fake DNS records are inserted into a DNS cache.

Future users are redirected to malicious servers.

---

### DNS Amplification

Attackers exploit DNS servers to launch Distributed Denial of Service (DDoS) attacks.

---

## Advantages

- Easy-to-remember website names
- Fast name resolution
- Distributed and scalable
- Supports load balancing through DNS records

---
