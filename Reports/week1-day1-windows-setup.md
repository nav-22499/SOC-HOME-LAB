
# Week 1 Day 1 — Windows SOC Endpoint Setup

## Objective

Deploy and configure the primary Windows endpoint used for telemetry collection, attack simulation, and SOC investigations.

---

## Tasks Completed

### VMware Network Configuration

Configured VMnet1 as a host-only isolated network.

Settings:

* Subnet: 192.168.56.0/24
* DHCP: Disabled

Reason:
To simulate an isolated enterprise network environment for safe attack simulations and centralized monitoring.

---

### Windows VM Deployment

Created Windows 10 virtual machine with:

* 4 GB RAM
* 2 CPU cores
* 60 GB disk

Purpose:
This VM will act as the primary enterprise workstation target.

---

### Static IP Configuration

Assigned:
192.168.56.10

Reason:
Static IPs simplify SIEM investigations and maintain consistent log source identification.

---

### Snapshot Creation

Created snapshot:
WIN10-CLEAN

Purpose:
Provides rollback capability for future attack simulations and troubleshooting.

---

## Key Concepts Learned

### Why Host-Only Networking?

Host-only networking isolates the lab from the internet while allowing communication between virtual machines.

### Why Static IP Addresses?

Static IP addresses allow consistent asset tracking during investigations and SIEM analysis.

### Why Windows Logging Matters?

Windows endpoints generate valuable security telemetry including:

* authentication logs
* process creation logs
* PowerShell activity
* service installation events

---

## Screenshots Captured

* VMware network configuration
* Windows VM settings
* Static IP configuration
* ipconfig verification
* Snapshot creation

---

## Next Steps

* Deploy Ubuntu server
* Configure Linux logging
* Deploy Kali attacker machine
* Install Splunk SIEM
