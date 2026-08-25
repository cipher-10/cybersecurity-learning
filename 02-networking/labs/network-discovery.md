# Lab — Authorized Network Discovery

## Objective

Identify the local lab host, discover exposed services, and document the results without scanning unauthorized systems.

## Environment

- Attacker: Kali Linux or another security workstation
- Target: Local training VM owned by me / explicitly authorized
- Network: Host-only or isolated lab network
- Tool: Nmap

## Procedure

1. Identify the target IP from the lab configuration.
2. Confirm the target is an authorized training system.
3. Run a basic service discovery scan.
4. Record open ports and detected services.
5. Compare the result with services intentionally enabled on the VM.
6. Document unexpected exposure and recommended hardening.

## Commands

```bash
nmap -sV <LAB_IP>
nmap -p 22,80,443,445,3389 <LAB_IP>
nmap -sC -sV <LAB_IP>
```

## Evidence to Capture

- Target IP and lab topology
- Nmap command used
- Sanitized Nmap output
- Table of discovered ports/services
- Explanation of why each exposed service exists
- Hardening recommendation for unnecessary services

## Findings Template

| Port | Service | Expected? | Risk observation | Recommendation |
|---:|---|---|---|---|
|  |  |  |  |  |

## Learning Questions

- What is the difference between a port being open, closed, and filtered?
- Why is service/version detection useful to a defender?
- Why should scanning be restricted to authorized systems?
- Which exposed services would deserve priority during triage?

## Safety

This lab must use an isolated or explicitly authorized target. Never copy these commands to scan public systems without permission.
