# Lab — ICMP Packet Analysis with Wireshark

## Objective

Capture an ICMP exchange and explain the packet fields and network flow.

## Environment

- Workstation: Windows or Linux
- Capture tool: Wireshark
- Target: `127.0.0.1` or an authorized lab host

## Procedure

1. Start Wireshark on the correct interface.
2. Start a capture.
3. Generate ICMP traffic to an authorized target.
4. Stop the capture after several packets.
5. Apply the display filter:

```text
icmp
```

6. Select an Echo Request and its Echo Reply.
7. Record source, destination, packet type, identifier, sequence number, and timing.

## Windows Example

```powershell
ping 127.0.0.1 -n 4
```

## Linux Example

```bash
ping -c 4 127.0.0.1
```

## Analysis

Document:

- Source IP
- Destination IP
- ICMP type/code
- Request/reply relationship
- Sequence numbers
- Approximate round-trip time
- Any packet loss

## Security Relevance

ICMP is useful for connectivity troubleshooting and network visibility. Abnormal ICMP patterns can also be relevant during security investigations, so analysts should understand normal behavior before treating traffic as suspicious.

## Evidence

Attach a sanitized screenshot showing the packet list and one expanded ICMP packet. Do not publish private IPs, credentials, tokens, or other sensitive information.
