 # Network Troubleshooting Lab (DHCP Failure & Restoration)

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
