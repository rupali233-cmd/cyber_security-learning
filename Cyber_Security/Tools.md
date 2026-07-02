# Wireshark

## What is Wireshark?

- Wireshark is a network packet analyzer.
- It captures and analyzes network traffic in real time.
- Used by network engineers and cybersecurity professionals to troubleshoot and investigate network issues.

---

## Main Uses

- Capture network packets.
- Analyze network traffic.
- Troubleshoot network problems.
- Detect suspicious or malicious activity.
- Learn how network protocols work.

---

## Features

- Free and open-source.
- Captures live network traffic.
- Supports hundreds of protocols.
- Displays packet details.
- Powerful filtering options.

---

## Packet Capture Process

1. Select a network interface (Wi-Fi or Ethernet).
2. Start capturing packets.
3. Perform network activity (browse a website, ping a device, etc.).
4. Stop the capture.
5. Analyze the packets using filters.

---

## Packet Information

Each captured packet contains:

- Source IP Address
- Destination IP Address
- Source Port
- Destination Port
- Protocol
- Packet Length
- Timestamp

---

## Common Protocols Seen in Wireshark

protocol and its purpose :-
 ARP => Finds MAC address from IP 
 ICMP =>  Ping messages 
TCP => Reliable communication 
 UDP => Fast communication 
HTTP => Web traffic 
HTTPS => Secure web traffic 
 DNS => Resolves domain names 
 DHCP => Assigns IP addresses 

---

---

## Useful Filters

```
ip.addr == 192.168.1.10
```
Shows packets sent to or from this IP.

```
ip.src == 192.168.1.10
```
Shows packets from the source IP.

```
ip.dst == 192.168.1.10
```
Shows packets to the destination IP.

```
tcp.port == 80
```
Shows HTTP traffic.

```
tcp.port == 443
```
Shows HTTPS traffic.

```
udp.port == 53
```
Shows DNS traffic.

```
http.request
```
Shows only HTTP requests.

```
http.response
```
Shows only HTTP responses.

---

## Capture Filters

Capture filters are applied **before** capturing packets.

Examples:

```
host 192.168.1.10
```

```
port 80
```

```
tcp
```

```
udp
```

---

## Difference Between Capture Filter and Display Filter

| Capture Filter            |       Display Filter |

| Applied before capture    | Applied after capture |
| Reduces captured traffic  | Filters existing packets |
| Uses BPF syntax           | Uses Wireshark syntax |

---

## Advantages

- Easy to analyze network traffic.
- Detects network issues.
- Helps in packet analysis.
- Useful for cybersecurity investigations.
- Supports many protocols.

---

## Limitations

- Cannot decrypt encrypted HTTPS traffic without the required keys.
- Capturing large amounts of traffic can consume memory.
- Requires permission to capture network traffic.

---

## Interview Questions

### What is Wireshark?

A network packet analyzer used to capture and inspect network traffic.

### Is Wireshark free?

Yes, it is free and open-source.

### What is a packet?

A small unit of data transmitted over a network.

### What is the difference between Capture Filter and Display Filter?

Capture filters select packets before capture, while display filters filter packets after they have been captured.

### Which protocol is used for secure web browsing?

HTTPS (TLS).

---

## Commands / Filters to Remember

```
ip
tcp
udp
arp
icmp
dns
http
tls
ip.addr == x.x.x.x
tcp.port == 80
tcp.port == 443
udp.port == 53
http.request
http.response
```

---

## My Notes

- Wireshark captures packets in real time.
- Display filters help analyze specific packets.
- Capture filters reduce unnecessary traffic before capturing.
- I can use Wireshark to analyze HTTP, DNS, ARP, TCP, and UDP traffic.
