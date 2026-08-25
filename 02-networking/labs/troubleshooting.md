# Lab — Network Troubleshooting

## Objective

Practice diagnosing a failed TCP connection using native operating-system tools.

## Scenario

A service is expected to be reachable from the workstation, but the TCP connection fails.

## Procedure

1. Confirm the local interface has a valid address.
2. Check the route to the destination.
3. Test basic reachability where appropriate.
4. Test the specific TCP port.
5. Resolve the hostname if a domain name is involved.
6. Compare the results and identify the most likely failure point.

## Windows

```powershell
ipconfig /all
route print
ping <TARGET_IP>
Test-NetConnection <TARGET_IP> -Port <PORT>
nslookup <HOSTNAME>
```

## Linux

```bash
ip addr
ip route
ping -c 4 <TARGET_IP>
ss -tulpen
dig <HOSTNAME>
curl -v http://<TARGET_IP>:<PORT>/
```

## Investigation Table

| Test | Result | Interpretation |
|---|---|---|
| Interface configuration |  |  |
| Route |  |  |
| ICMP reachability |  |  |
| TCP port test |  |  |
| DNS resolution |  |  |
| Application test |  |  |

## Possible Causes

- Incorrect IP address
- Missing route
- Host offline
- Firewall filtering
- Service not listening
- DNS resolution problem
- Application-layer failure

## Final Report

State the evidence that supports the diagnosis. Avoid claiming a firewall or service failure without a test that supports it.

## Safety

Use only systems and services that you own or are explicitly authorized to troubleshoot.
