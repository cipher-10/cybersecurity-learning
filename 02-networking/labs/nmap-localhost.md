# Nmap Localhost Enumeration

## Objective

Identify TCP services exposed by my own Windows system using Nmap and correlate the results with Windows listening services.

## Environment

- OS: Windows
- Tool: Nmap
- Target: `127.0.0.1` (localhost)
- Authorization: Personal/local system

## Commands

Basic port scan:

```powershell
nmap 127.0.0.1
```

Service/version detection:

```powershell
nmap -sV 127.0.0.1
```

Save scan output locally for evidence:

```powershell
nmap -sV 127.0.0.1 -oN nmap-localhost.txt
```

Check Windows listening TCP ports:

```powershell
Get-NetTCPConnection -State Listen |
Select-Object LocalAddress,LocalPort,OwningProcess
```

Check the Remote Desktop service when relevant:

```powershell
Get-Service TermService
```

## Results

Record only the ports that actually appeared in the scan.

| Port | Protocol | State | Service | Security Observation |
|---:|---|---|---|---|
| Add observed result | TCP/UDP | Open/Closed/Filtered | Service name | Why it matters |

## Analysis

Nmap was used to discover services exposed on localhost. The `-sV` option attempts to identify the service and version associated with an open port.

The Nmap results can be compared with Windows listening sockets to verify whether a local service is actually accepting connections.

The important security concept is:

```text
Windows service/process
        ↓
Listening socket
        ↓
TCP/UDP port
        ↓
Network attack surface
```

An open port is not automatically a vulnerability. The service, configuration, exposure, authentication, and software version must be investigated before assigning risk.

## What I Learned

- Nmap can enumerate network services.
- `-sV` performs service/version detection.
- Windows listening ports can be inspected with PowerShell.
- Service exposure is part of the system's attack surface.
- Enumeration should be performed only against systems I own or have explicit authorization to test.

## Evidence

Add a sanitized screenshot of the Nmap output and, where useful, the matching PowerShell listening-port output.

Do not publish credentials, tokens, public IP addresses, or other sensitive information.

## Authorization

This exercise was performed only against my own localhost system for educational purposes.
