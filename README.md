 Network Troubleshooting Lab (DHCP Failure & Restoration)

## Overview
This project simulates a real-world network troubleshooting scenario using Cisco Packet Tracer. The objective was to identify a DHCP failure, diagnose the root cause, and restore network connectivity by reconfiguring the DHCP service on a router.

---

## Problem Description
The client PC was unable to obtain an IP address automatically from the DHCP server. As a result, the device had no valid network configuration and could not communicate on the network.

---

## Step 1: DHCP Failure

The PC failed to obtain an IP address from the DHCP server.

### Evidence
- Message displayed: **DHCP failed**

### Screenshot
![DHCP Failure](screenshots/08-dhcp-failure.png)

---

## Step 2: Diagnose the Problem

The following command was used to investigate the issue:

```bash
ipconfig
Findings
IP Address: 169.254.x.x (APIPA address)
Subnet Mask: 255.255.0.0
Default Gateway: 0.0.0.0
Interpretation

The APIPA address indicates that the PC could not reach a DHCP server and automatically assigned itself a fallback IP.

Screenshot

Step 3: Root Cause Analysis

The DHCP pool responsible for assigning IP addresses to the LAN was missing or deleted on the router:

DHCP pool name: LAN_A
Result: No IP addresses could be assigned to clients
Step 4: Fix Applied (DHCP Restoration)

The DHCP service was restored on the router using the following configuration:

enable
configure terminal
ip dhcp pool LAN_A
network 192.168.10.0 255.255.255.0
default-router 192.168.10.1
dns-server 8.8.8.8
end
Step 5: Verification

After restoring DHCP, the client successfully received a valid IP address automatically.

Expected Results
IP Address: 192.168.10.x
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.10.1
Screenshot

Skills Demonstrated
DHCP troubleshooting and configuration
Cisco router CLI configuration
Network diagnostics using ipconfig
Identification of APIPA (169.254.x.x) addressing
Root cause analysis and resolution
Real-World Relevance

This scenario simulates a common enterprise network failure where DHCP misconfiguration prevents devices from obtaining valid IP addresses. Resolving such issues ensures network availability and proper client connectivity.

Conclusion

The DHCP service was successfully restored, and all client devices regained network connectivity by receiving valid IP configurations automatically.
