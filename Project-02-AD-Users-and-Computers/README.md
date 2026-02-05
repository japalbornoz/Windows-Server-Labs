# Project 02: Active Directory Users and Computers Testing (SIGMA Lab)
*User and computer account management, OU structure, and permissions testing.*

This project demonstrates how to create, manage, and test user and computer accounts in Active Directory. It focuses on identity management, group membership, and file access permissions within a domain environment.

---

## 🧱 Lab Architecture

- **Domain Controller**: SIGMA-DC1 (192.168.0.254)
- **Member Servers**: SIGMA-SVR1, SIGMA-CORE
- **IT HelpDesk**: SIGMA-ITSUPP
- **User Workstation**: SIGMA-USER (Windows 11 Enterprise)

Domain: `sigmanetwork.local`

---

## 🔑 User Account Management

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

📸 **Lab Infrastructure Preview**:
- Creating a TSR OU inside Manila>Users OU                                                           
  <img src="User%20Account%20Management/createoutsr.png" width="500">
- User and Group creation in ADUC                         
  <img src="User%20Account%20Management/createuser.png" width="500">
  <img src="User%20Account%20Management/creategroup.png" width="500">
- Group membership properties                                   
  <img src="User%20Account%20Management/itgroup.png" width="500">
  <img src="User%20Account%20Management/csrgroup.png" width="500">
- Successful domain login                                          
  <img src="User%20Account%20Management/itsupp.png" width="500">

---

## 🖥️ Computer Account Management

### Tasks Completed
- Verified domain join for SIGMA-SVR1, SIGMA-CORE, ITSUPPORT, and USER.
- Moved computer objects into Organizational Units (OUs):
  - `Servers OU`
  - `Workstations OU`
- Tested login restrictions and group policies applied to computers.

📸 **Screenshots**:
- ADUC showing computer objects in OUs
- Properties of a domain-joined workstation

---

## 📂 File and Folder Permissions

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

📸 **Screenshots**:
- Folder security properties
- Access tests from different accounts

---

## 🧠 Lessons Learned

- Group membership simplifies permission management compared to per-user settings.
- OU structure helps organize and apply policies to specific sets of users/computers.
- Testing access with multiple accounts is essential to validate security design.
- Documenting screenshots provides clear proof of configuration and results.

---

## 🚀 Next Steps

- Expand OU structure with role-based design (e.g., `Finance`, `HR`).
- Apply Group Policy Objects (GPOs) for password policies and desktop restrictions.
- Integrate with DNS/DHCP (covered in Project 04).
