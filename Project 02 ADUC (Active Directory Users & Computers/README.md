# Project 02: Active Directory Users and Computers Testing (SIGMA Lab)
*User and computer account management, OU structure, and permissions testing.*

This project demonstrates how to create, manage, and test user and computer accounts in Active Directory. It focuses on identity management, group membership, and file access permissions within a domain environment.

---

## Lab Architecture

- **Domain Controller**: SIGMA-DC1 (192.168.0.254)
- **Member Servers**: SIGMA-SVR1, SIGMA-CORE
- **IT HelpDesk**: SIGMA-ITSUPP
- **User Workstation**: SIGMA-USER (Windows 11 Enterprise)

Domain: `sigmanetwork.local`

---

## User Account Management

### Tasks Completed
- Created Main OU (Manila) with Sub-OUs (Computers, Users)
- Created, e.g., IT, CSR Sub-OUs of Manila>Users OU
- Created test user accounts (e.g., `jap.albornoz`, `ra.duque`, `delaila.castro`).
- Configured password policies (complexity, expiration).
- Assigned users to security groups:
  - **Domain Users** (default)
  - **IT Group**
  - **CSR Group**
- Tested login from SIGMA-ITSUPP-W11 workstation.

**Lab Infrastructure Preview**:
- Creating a TSR and CSR OUs inside Manila>Users OU                                                                  
  <img src="User%20Account%20Management/createoutsr.png" width="500">
  
- User and Group creation in ADUC                            
  <img src="User%20Account%20Management/createuser.png" width="500">
  <img src="User%20Account%20Management/creategroup.png" width="500">
  
- Group membership properties                                          
  <img src="User%20Account%20Management/itgroup.png" width="500">
  <img src="User%20Account%20Management/csrgroup.png" width="500">
  
- Successful domain login                                                     
  <img src="User%20Account%20Management/itsupp.png" width="500">
  
- Assigned a User/Group (IT-Users) to be part of the DC Administrator                                                
  <img src="User%20Account%20Management/ituser1.png" width="300"><img src="User%20Account%20Management/ituser2.png" width="300">
  
- Adding DC's Group (IT-Users) manually to the Local Administrators group on other servers (SIGMA‑SVR1, SIGMA‑CORE)                 
  <img src="User%20Account%20Management/local1.png" width="500">                                                          
  <img src="User%20Account%20Management/local3.png" width="300"><img src="User%20Account%20Management/local2.png" width="300">
  <img src="User%20Account%20Management/core1.png" width="500">
                                       
- Verify `jap.albornoz` user from the IT-Users group can log in to the servers                                                
  <img src="User%20Account%20Management/core2.png" width="500">
  <img src="User%20Account%20Management/svr1.png" width="500">
---

## Computer Account Management

### Tasks Completed
- Moved computer objects into Organizational Units (OUs):
  - `Servers OU`
  - `Workstations OU`
- Tested login restrictions and group policies applied to computers.

📸 **Lab Infrastructure Preview**:
- ADUC showing computer objects in Servers or Workstations OUs                  
  <img src="Computer%20Account%20Management/computerserver.png" width="500">
  <img src="Computer%20Account%20Management/computerserver2.png" width="500">
- Properties of a domain-joined Server or Workstation                       
  <img src="Computer%20Account%20Management/svr1.png" width="500">
---

## File and Folder Permissions

### Tasks Completed
- Created shared folder on SIGMA-SVR1.
- Applied NTFS permissions:
  - **IT Support Group** → Full Control
  - **CSR Group** → Read/Write
  - **Domain Users** → Read-only
- Tested access from SIGMA-USER-W11:
  - IT Support user can modify files.
  - CSR user can create/edit files.
  - Standard user can only read.

 **GPO Implementation & Validation**:
- Folder security properties                                             
  <img src="File%20and%20Folder%20Permissions/cfolder.png" width="500">
  <img src="File%20and%20Folder%20Permissions/fsp1.png" width="500">
  <img src="File%20and%20Folder%20Permissions/fsp2.png" width="500">
- Access tests from different accounts, example SIGMA-DC1                                
  <img src="File%20and%20Folder%20Permissions/test1.png" width="500">
  <img src="File%20and%20Folder%20Permissions/test2.png" width="500">
---

## Lessons Learned 
- Group membership simplifies permission management compared to per-user settings.
- OU structure helps organize and apply policies to specific sets of users/computers.
- Testing access with multiple accounts is essential to validate security design.
- Documenting screenshots provides clear proof of configuration and results.

- Promoting a server to Domain Controller removes local SAM accounts; only domain accounts/groups remain.
- Domain Admins are automatically added to local Administrators on member servers.
- Local Administrator accounts are machine‑only and cannot log in to other domain machines.
- Custom groups (like IT‑Users) must be manually delegated or automated via GPO.
- Discovered that broken trust relationships prevent even Domain Admins from logging in, requiring a rejoin or computer account reset in ADUC.
- Learned the difference between **domain‑wide authority** (Domain Admins) and **machine‑specific authority** (local admins).
- Testing with different accounts validates that permissions match intended access

---

## Next Steps

- Expand OU structure with role-based design (e.g., `Finance`, `HR`).
- Apply Group Policy Objects (GPOs) for password policies and desktop restrictions.
- Integrate with DNS/DHCP (covered in Project 04).
