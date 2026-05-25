# Incident Resolution & Knowledge Base Documentation

## 1. Executive Summary
* **Issue Title:** Lack of IPv4 Connectivity on Network Interface ens33 due to Missing Minimal OS Packages in Ubuntu 26.04 LTS.
* **Date / Environment:** May 2026 / VMware Environment running a Custom VMnet8 (NAT) configuration.
* **Impact:** The guest operating system had no outbound internet access or local routing capability, restricting package installation and system updates.
* **Status:** **Resolved**

---

## 2. Problem Description & Error Breakdown
During the post-installation phase of an ultra-minimal Ubuntu 26.04 LTS deployment, the secondary interface card (`ens33`) failed to negotiate an IPv4 address with the VMware host DHCP server.

### Core Roadblocks Faced:
1. **Missing IPv4 Configuration:** Running `ip a` displayed a physical link state of `UP` and a valid Link-Local IPv6 address (`fe80::...`), but completely lacked an `inet` (IPv4) address block.
2. **Missing Standard Networking Utilities:** Attempting a manual DHCP solicitation via `sudo dhclient -v ens33` failed with:
   > `sudo: 'dhclient': command not found`
3. **Missing Essential Text Editors:** Attempting to modify the underlying YAML configurations via `sudo nano` failed with:
   > `sudo: 'nano': command not found`

---

## 3. Root Cause Analysis (RCA)
* **OS Profile Minimalization:** The Ubuntu image deployed was optimized for a minimal footprint. Standard diagnostics, networking daemons (like `isc-dhcp-client`), and user-space editors (`nano`) were excluded from the base layer image.
* **Unconfigured Netplan State:** The initial `00-installer-config.yaml` layout created during installation either failed to parse correctly, used an unmapped adapter name, or lacked explicit parameters instructing the `systemd-networkd` renderer to initiate a DHCPv4 request on the `ens33` bus.

---

## 4. Detailed Step-by-Step Resolution
Because the operating system completely lacked internet connectivity, standard package retrieval (`apt install`) was impossible. The system had to be manually reconfigured using core bash built-ins.

### Step 4.1: Direct Netplan Overwrite via Stream Redirection
Without `nano` or `vim`, a Here-Document (`<< 'EOF'`) combined with the `tee` utility was used to overwrite the Netplan configuration layout directly from standard input.

```bash
sudo tee /etc/netplan/00-installer-config.yaml << 'EOF'
network:
  version: 2
  renderer: networkd
  ethernets:
    ens33:
      dhcp4: true
EOF
