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

Ref 1: OU Structure

![OU_Structure](Documentation/OU_Structure.png)

---

## GPOs
| Name                           | Linked To      | Key Settings                           |
|-------------------------------|----------------|----------------------------------------|
| SalesUsers-DesktopRestrictions| Sales_Users OU | Disable CMD, Regedit, Control Panel    |
| HRUsers-DesktopRestrictions   | HR_Users OU    | Similar restrictions                   |
| Login Banner GPO              | Computers OU or Domain | Interactive logon text and title     |

---

## Security Groups and Membership
Stored in `Documentation/GroupMemberships.csv`

| User       | Groups                                  |
|------------|-----------------------------------------|
| Lab Admin  | Domain Users, Administrators            |
| Sales Test | Domain Users, Sales_ReadAccess          |
| HR Test    | Domain Users, HR_ReadAccess             |

---

## Folder Permissions

**Sales Folder**:
- Location: `C:\Shares\Sales`
- Group: `Sales_ReadAccess`
- Access: Read-only

**HR Folder**:
- Location: `C:\Shares\HR`
- Group: `HR_ReadAccess`
- Access: Read-only

Ref 2: Sales Share Permissions

![Sales_Share_Permissions]


---

## Compliance: Login Banner (AU-8)

![Login Banner](Documentation/Login_Banner.png)

---

## Results

### Group Policy Results (Sales User)
`gpresult_sales.html` included in `/Documentation`.

Key Policies Applied:
- Login Banner
- Desktop Restrictions
- Security Group Access

---

## Notes
- Computers should be moved from `Computers` to `Lab-Computers` for scoped GPOs.
- Group membership listing was manually validated.
