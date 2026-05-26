# SOC-HOME-LAB
SOC Analyst home lab with Splunk, Sysmon, Wazuh, threat hunting, and detection engineering



# SOC Home Lab

Objective

This project documents the development of a practical SOC Analyst home lab designed for:

* SIEM analysis
* Windows log analysis
* Sysmon telemetry
* Threat hunting
* Detection engineering
* Incident investigations
* Attack simulations

---

Lab Architecture

The lab environment consists of:

| Machine       | Purpose             |
| ------------- | ------------------- |
| Windows 10    | Victim workstation  |
| Kali Linux    | Attack simulation   |
| Ubuntu Server | Linux logging       |
| Splunk        | SIEM platform       |
| Wazuh         | Endpoint monitoring |

---

Network Configuration

| Host        | IP Address    |
| ----------- | ------------- |
| SOC-WIN10   | 192.168.56.10 |
| SOC-KALI    | 192.168.56.20 |
| SOC-UBUNTU  | 192.168.56.30 |
| SPLUNK-SIEM | 192.168.56.40 |
| WAZUH       | 192.168.56.50 |

---

Technologies Used

* VMware Workstation
* Splunk Enterprise
* Sysmon
* Wazuh
* Windows Event Logs
* Linux Logs
* Wireshark
* MITRE ATT&CK

---

Current Progress

Week 1

* [x] VMware network configured
* [x] Windows 10 VM deployed
* [x] Static IP configuration completed
* [x] Snapshot created

---

Future Goals

* Sysmon deployment
* Splunk ingestion
* Detection engineering
* Threat hunting
* Incident response investigations

  Week 1
- [x] VMware network configured
- [x] Windows 10 VM deployed
- [x] Ubuntu Linux server deployed
- [x] SSH service configured
- [x] Linux logging validated

### Week 1
- [x] VMware network configured
- [x] Windows 10 VM deployed
- [x] Ubuntu Linux server deployed
- [x] Kali attacker machine deployed
- [x] Reconnaissance simulations completed
