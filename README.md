# Sales-HR-GPO-AccessControl

This project simulates a real-world environment with departmental separation (Sales and HR) to apply GPO restrictions, enforce access control via security groups, and implement login banners for compliance (AU-8). Built in a virtual lab using VirtualBox and Windows Server.

---

## Features
- Organizational Units for HR and Sales users
- Security groups (`HR_ReadAccess`, `Sales_ReadAccess`)
- NTFS folder permissions mapped to AD groups
- GPOs restricting command prompt, regedit, control panel
- Login banner for compliance and auditing

---

## OU Design
- `Lab-Users/HR_Users`
- `Lab-Users/Sales_Users`
- `Lab-SecurityGroups`
- `Lab-Computers` (future scalable design)

Ref 1 OU Structure

<img width="641" height="463" alt="OU_Structure" src="https://github.com/user-attachments/assets/b35489da-f7c7-43da-8421-70818fa8fd22" />
