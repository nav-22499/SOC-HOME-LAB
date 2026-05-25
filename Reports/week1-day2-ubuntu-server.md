# Week 1 Day 2 — Ubuntu Server Deployment

## Objective

Deploy a Linux server for SSH logging, Linux event analysis, and future Splunk ingestion.

---

## Tasks Completed

### Ubuntu VM Deployment

Created Ubuntu virtual machine with:

* 4 GB RAM
* 2 CPU cores
* 30 GB storage

Purpose:
Simulate enterprise Linux infrastructure for SOC investigations.

---

### OpenSSH Configuration

Enabled SSH service during installation.

Purpose:
Allow remote access simulations and SSH investigation scenarios.

---

### Static IP Configuration

Assigned:
192.168.56.30

Reason:
Maintain consistent log source identification during SIEM investigations.

---

### Linux Authentication Logging

Investigated:

* /var/log/auth.log
* sudo activity
* authentication events

Purpose:
Understand Linux security telemetry used in SOC operations.

---

## Key Concepts Learned

### Why Linux Logging Matters

Linux systems generate valuable security logs including:

* SSH logins
* failed authentication attempts
* privilege escalation
* sudo activity

### Why SSH Monitoring Matters

SSH is frequently targeted in:

* brute-force attacks
* credential stuffing
* unauthorized remote access attempts

---

## Screenshots Captured

* Ubuntu VM settings
* Static IP configuration
* SSH service status
* auth.log output
* successful ping tests

---

## Next Steps

* Deploy Kali Linux attacker machine
* Begin attack simulations
* Configure Splunk SIEM
