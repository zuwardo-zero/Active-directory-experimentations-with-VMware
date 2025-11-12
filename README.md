# VMware Active Directory Lab with Group Policy Objects

This project demonstrates a custom **Active Directory lab** built in **VMware Workstation**, where multiple **Group Policy Objects (GPOs)** were configured and applied to domain-joined virtual machines.

---

## 🔧 Lab Setup
- **Domain Name:** Sci.dz  
- **Virtual Machines:**  
  - 1 Domain Controller (Windows Server 2008 R2)  
  - 2 Client Machines (Windows 10)  
- **Platform:** VMware Workstation  

---

## 📌 Implemented GPOs

### 1. USB Access Restriction
- **Path:** `Computer Configuration > Policies > Administrative Templates > System > Removable Storage Access`  
- Enabled **“All removable storage classes: Deny all access”**.  
- ✅ Prevents domain users from using USB devices on client machines.  

---

### 2. TCP/IP Settings Restriction
- **Path:** `User Configuration > Policies > Administrative Templates > Network > Network Connections`  
- Enabled **“Prohibit TCP/IP Advanced Configuration”**.  
- ✅ Prevents domain users from changing network adapter IP settings.  

---

### 3. Automatic Microsoft Office Installation
- **Path:** `Computer Configuration > Policies > Software Settings > Software Installation`  
- Added Microsoft Office package (converted `.exe` → `.msi` using **MSI Wrapper**) which was something different that i learned on the lab .  
- ✅ Automatically installs Office on client VMs after restart.  

---

## ⚠️ Important Notes
- GPOs must be **linked to the domain (for example department.dz)** to take effect.  
- Run `gpupdate /force` after changes for immediate policy refresh.  
- Software deployment requires `.msi` packages, not `.exe` .  

---


## 🛠 Skills Demonstrated
- Active Directory & Domain Controller setup  
- Group Policy Management  
- Security hardening (USB and network restrictions)  
- Automated software deployment via GPO  
- VMware virtualization for lab environments  

---

