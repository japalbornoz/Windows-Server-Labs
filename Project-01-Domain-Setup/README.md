# Project 01: Active Directory Domain Setup

This project documents the setup of a Windows Server 2022 Domain Controller in a fully isolated lab environment using VMware Workstation Pro.

---

## 🧱 Lab Architecture

- **Virtualization Platform**: VMware Workstation Pro
- **Operating Systems**: Windows Server 2022, Windows 11 Enterprise 
- **Network Type**: Host-only (VMnet1)
- **Network Address**: 192.168.0.0/24
- **Domain Name**: `sigmanetwork.local`




![Domain Promotion Wizard](./SIGMAVM.png)


## 🗂️ Network Partitioning

- **Server IP Range**: 192.168.0.240 – 192.168.0.254  
- **IT IP Range**: 192.168.0.220 – 192.168.0.239  
- **User IP Range**: 192.168.0.1 – 192.168.0.219
---

## 🔧 Setup Steps

1. Set up the five Virtual Machines in VMWare Workstation Pro
2. Installed Windows Server 2022 on SIGMA-DC1, SIGMA-SVR1, SIGMA-CORE
3. Installed Windows 11 (Enterprise) on ITSUPP and USER 
4. SIGMA-DC1 configuration, static IP: `192.168.0.254`, no gateway, DNS = self
5. Installed AD DS and DNS roles via Server Manager
6. Promoted SIGMA-DC1 to a domain controller (`sigmanetwork.local`)
7. Verified domain functionality and DNS resolution
8. Joined SIGMA-SVR1, SIGMA-CORE, SIGMA-ITSUPP, and SIGMA-USER to the domain

---

## 📸 Screenshots
- [x] Server Manager Role Installation  
- [x] Domain Promotion Wizard  
- [x] Successful domain join (SVR1, CORE, ITSUPP, USER)  
- [x] DNS zone configuration

---

## 🧠 Lessons Learned

- DNS must point to the DC during domain join  
- Manual IP setup avoids DHCP conflicts  
- Segmenting IP ranges improves clarity and future GPO targeting  
- Host-only VMnet ensures full isolation from the real network
  
---

## 🚀 Next Steps

- Create and apply Group Policy Objects by role  
- Add DNS forwarders and test external name resolution  
- Document troubleshooting scenarios (e.g., failed domain join, replication issues)
