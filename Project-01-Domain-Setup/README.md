# Project 01: Active Directory Domain Setup
*Active Directory domain controller promotion and domain join basics.*

This project documents the setup of a Windows Server 2022 Domain Controller in a fully isolated lab environment using VMware Workstation Pro.

---

## 🧱 Lab Architecture

- **Virtualization Platform**: VMware Workstation Pro
- **Operating Systems**: Windows Server 2022, Windows 11 Enterprise 
- **Network Type**: Host-only (VMnet1)

![Domain Promotion Wizard](./5VMs.drawio.png)

![Domain Promotion Wizard](./NPartitioning.png)

![Domain Promotion Wizard](./VMDiagram.png)
---

## 🔧 Setup Steps

A. VMWare Workstation Pro: Set up the five Virtual Machines
-  Installed Windows Server 2022 on SIGMA-DC1, SIGMA-SVR1, SIGMA-CORE
-  Installed Windows 11 (Enterprise) on ITSUPP and USER

B. Virtual Machine SIGMA-DC1
-  SIGMA-DC1 network configuration, static IP: `192.168.0.254`, no gateway, DNS = self
-  Installed AD DS, DNS, DHCP, and Group Policy Management via Server Manager roles and features
-  Promoted SIGMA-DC1 to a domain controller (`sigmanetwork.local`)

C. Virtual Machines SIGMA-SVR and SIGMA-CORE
-  SIGMA-SVR network configuration, static IP: `192.168.0.253`, no gateway, DNS: `192.168.0.254`
-  SIGMA-CORE network configuration, static IP: `192.168.0.252`, no gateway, DNS: `192.168.0.254`
-  Joined the domain (sigmanetwork)

D. Virtual Machines SIGMA-IT and SIGMA-USER
-  SIGMA-IT network configuration, static IP: `192.168.0.241`, no gateway, DNS: `192.168.0.254`
-  SIGMA-USER network configuration, static IP: `192.168.0.1`, no gateway, DNS: `192.168.0.254`
-  Joined the domain (sigmanetwork)  

---

## 📸 Environment Topology
- [x] **Server Manager Role Installation**             
      <img src="Server%20Manager%20Role%20Installation/installation%20part1.png" width="600">
      <img src="Server%20Manager%20Role%20Installation/installation%20part2.png" width="600">

- [x] **Domain Promotion Wizard**                
      <img src="Domain%20Promotion%20Wizard/SIGMA-DC1%20network%20config.png" width="600">
      <img src="Domain%20Promotion%20Wizard/SIGMA-DC1%20as%20DC.png" width="300"><img src="Domain%20Promotion%20Wizard/SIGMA-DC1%20as%20DC%202.png" width="400">


- [x] **Successful Domain Join (SVR1, CORE, ITSUPP, USER)**
      <img src="Domain%20Join/VMWARE%20Overview.png" width="600">
      <img src="Domain%20Join/ALL.png" width="600">
      <img src="Domain%20Join/CORE.png" width="600">
      <img src="Domain%20Join/IT.png" width="300"><img src="Domain%20Join/USER.png" width="294">
      

      
 
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
