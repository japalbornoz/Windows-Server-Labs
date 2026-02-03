# Project 01: Active Directory Domain Setup

This project documents the setup of a Windows Server 2022 Domain Controller in a fully isolated lab environment using VMware Workstation Pro.

---

## 🧱 Lab Architecture

- **Virtualization Platform**: VMware Workstation Pro
- **Network Type**: Host-only (VMnet1), manual IP configuration
- **Subnet**: 192.168.1.0/24
- **Domain Name**: lab.local

| VM Name   | Role               | IP Address       |
|-----------|--------------------|------------------|
| RTS-DC1   | Domain Controller  | 192.168.1.250    |
| RTS-SVR1  | Member Server      | 192.168.1.251    |
| RTS-CORE  | Client / Utility   | 192.168.1.252    |

---

## 🔧 Setup Steps

1. Installed Windows Server 2022 on RTS-DC1
2. Configured static IP: `192.168.1.250`, no gateway, DNS = self
3. Installed AD DS and DNS roles via Server Manager
4. Promoted RTS-DC1 to a domain controller (`lab.local`)
5. Verified domain functionality and DNS resolution
6. Joined RTS-SVR1 and RTS-CORE to the domain

---

## 📸 Screenshots
![image alt](https://github.com/japalbornoz/Windows-Server-Labs/blob/9eef76f5f0c671ca791751d6379cf68f42c50b7a/Screenshot%202026-02-03%20090632.png)
![Domain Promotion Wizard](./image01.png)
![Domain Promotion Wizard](./domain-promotion.png)
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
