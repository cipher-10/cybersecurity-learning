# Networking Notes

## OSI Model

| Layer | Name | Security relevance |
|---|---|---|
| 7 | Application | HTTP, DNS, APIs, web attacks |
| 6 | Presentation | Encoding, encryption, serialization |
| 5 | Session | Session establishment and management |
| 4 | Transport | TCP/UDP, ports, connections |
| 3 | Network | IP addressing, routing, ICMP |
| 2 | Data Link | MAC, ARP, switching, VLANs |
| 1 | Physical | Signals, cables, radio |

## TCP/IP Model

- Application: HTTP, HTTPS, DNS, SSH, SMTP
- Transport: TCP and UDP
- Internet: IP, ICMP
- Network Access: Ethernet, Wi-Fi, ARP

## TCP vs UDP

**TCP** is connection-oriented and provides reliable, ordered delivery. It uses mechanisms such as the three-way handshake.

**UDP** is connectionless and has lower protocol overhead. It is useful where speed and application-level handling are preferred.

## Common Ports

| Port | Protocol | Typical use |
|---:|---|---|
| 22 | SSH | Secure remote administration |
| 53 | DNS | Name resolution |
| 80 | HTTP | Web traffic |
| 443 | HTTPS | Encrypted web traffic |
| 3389 | RDP | Windows remote desktop |
| 445 | SMB | Windows file/printer sharing |
| 25 | SMTP | Mail transfer |
| 110 | POP3 | Mail retrieval |
| 143 | IMAP | Mail retrieval |

## DNS

DNS maps names to network addresses and other records. Security analysis often looks at unusual domains, query volume, record types, and resolver behavior.

## DHCP

DHCP automatically provides network configuration such as an IP address, subnet mask, gateway, and DNS server.

## ARP

ARP resolves an IPv4 address to a MAC address on a local network. ARP behavior is useful when investigating local-network connectivity and possible spoofing.

## ICMP

ICMP carries network control and diagnostic messages. `ping` commonly uses ICMP Echo Request and Echo Reply.

## HTTP/HTTPS

HTTP is an application-layer protocol used for web communication. HTTPS is HTTP protected by TLS.

When analyzing web traffic, inspect:

- Method
- Host
- URI/path
- Status code
- Headers
- Content type
- Source and destination
- TLS metadata for HTTPS

## Security Perspective

Networking knowledge supports:

- SOC alert triage
- Packet analysis
- Network reconnaissance
- Firewall troubleshooting
- Incident response
- Cloud network security
- Web-security testing
