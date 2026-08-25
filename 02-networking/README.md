# 02 — Networking for Cybersecurity

Networking is the foundation for SOC analysis, VAPT, cloud security, and incident response.

## Learning Objectives

- Explain OSI and TCP/IP models
- Understand IPv4, subnetting, routing, and NAT
- Distinguish TCP and UDP
- Identify common ports and protocols
- Understand DNS, DHCP, ARP, and ICMP
- Read HTTP/HTTPS traffic
- Use Nmap for authorized discovery and enumeration
- Use Wireshark to analyze packets
- Troubleshoot connectivity with native OS tools

## Study Order

1. OSI model
2. TCP/IP model
3. IPv4 addressing
4. Subnetting
5. TCP vs UDP
6. Ports and protocols
7. DNS / DHCP / ARP / ICMP
8. Routing and NAT
9. HTTP / HTTPS
10. Nmap
11. Wireshark
12. Troubleshooting

## Core Commands

### Windows PowerShell

```powershell
ipconfig /all
ping 127.0.0.1
tracert example.com
nslookup example.com
Test-NetConnection example.com -Port 443
Get-NetTCPConnection
```

### Linux

```bash
ip addr
ip route
ping -c 4 127.0.0.1
traceroute example.com
ss -tulpen
dig example.com
curl -I https://example.com
```

### Nmap — authorized targets only

```bash
nmap -sV <LAB_IP>
nmap -p 22,80,443 <LAB_IP>
nmap -sC -sV <LAB_IP>
```

## Portfolio Labs

- [ ] Identify my lab network and interfaces
- [ ] Capture and explain an ICMP exchange
- [ ] Resolve a domain and document DNS traffic
- [ ] Compare TCP and UDP behavior
- [ ] Enumerate a local training VM with Nmap
- [ ] Capture an HTTP request in Wireshark
- [ ] Investigate a failed TCP connection
- [ ] Write a network troubleshooting report

## Evidence Standard

For each lab, publish:

- Objective
- Lab topology
- Commands/tools used
- Sanitized output or screenshots
- Analysis of what happened
- Security relevance
- Defensive observation
- Lessons learned

## Safety

Use Nmap, packet capture, and enumeration only against systems you own or environments where you have explicit authorization. Do not scan public targets without permission.

## Completion Rule

Do not mark a networking topic complete after watching a lecture alone. Explain the concept, demonstrate it in a controlled lab, and document the evidence.
