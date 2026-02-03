# Project 01: Active Directory Domain Setup

This project documents the setup of a Windows Server 2022 Domain Controller in a fully isolated lab environment using VMware Workstation Pro.

---

## 🧱 Lab Architecture

- **Virtualization Platform**: VMware Workstation Pro
- **Network Type**: Host-only (VMnet1), manual IP configuration
- **Network**: 192.168.1.0/24
- **Domain Name**: sigmanetwork.local

![Domain Promotion Wizard](./SIGMAVM.png)

---

## 🔧 Setup Steps

1. Installed Windows Server 2022 on SIGMA-DC1
2. Configured static IP: `192.168.1.250`, no gateway, DNS = self
3. Installed AD DS and DNS roles via Server Manager
4. Promoted SIGMA-DC1 to a domain controller (`sigmanetwork.local`)
5. Verified domain functionality and DNS resolution
6. Joined SIGMA-SVR1 and SIGMA-CORE to the domain

---

## 📸 Screenshots
- [x] Server Manager Role Installation  
- [x] Domain Promotion Wizard  
- [x] Successful domain join (SRV1, CORE)  
- [x] DNS zone configuration

---

## 🧠 Lessons Learned

- Importance of DNS pointing to DC during domain join  
- Manual IP setup avoids DHCP conflicts  
- Host-only VMnet ensures full isolation from real network

---

## 🚀 Next Steps

- Create and apply Group Policy Objects  
- Add DNS forwarders and test name resolution  
- Document troubleshooting scenarios (e.g., failed domain join)
