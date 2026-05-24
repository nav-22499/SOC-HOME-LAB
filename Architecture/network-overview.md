 SOC Lab Network Overview

 Network Design

The SOC lab uses an isolated host-only VMware network.

Subnet:
192.168.56.0/24

Purpose:

* isolate attack simulations
* centralize monitoring
* simulate enterprise internal network traffic

---

Machines

SOC-WIN10

Primary Windows endpoint used for:

* Sysmon telemetry
* PowerShell logging
* authentication events

SOC-KALI

Attacker simulation platform used for:

* reconnaissance
* scanning
* brute-force simulations

SOC-UBUNTU

Linux server used for:

* SSH logging
* Linux event analysis

SPLUNK-SIEM

Centralized logging and SIEM platform.

WAZUH

Endpoint monitoring and detection platform.

