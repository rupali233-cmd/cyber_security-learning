
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


