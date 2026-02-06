## GPOs

## Created GPOs

![GPOs Overview](./images/GPOs.png)

One GPO was created per Organizational Unit, following the best practice of not applying GPOs directly to individual objects. The following GPOs were created:

- Baseline Workstations  
- IT-Admins  
- IT-Users  
- HR-Users  
- Finance-Users  

Each GPO was linked to its respective OU.

---

## GPO Rules

The GPOs were designed based on user roles and basic security requirements. A baseline GPO was applied to all workstations to enforce account lockout policies, enable auditing for authentication and account management events, and disable insecure features such as SMBv1 and guest logons. This baseline also ensures that security events are generated for monitoring by Wazuh.

Administrative access was handled through a dedicated IT-Admins GPO, where the ITadmins group was added to the local Administrators group on domain workstations, allowing privileged access only to authorized users.

Department-specific GPOs were created for HR and Finance users. HR users were restricted from accessing the Command Prompt and Control Panel to limit system changes, while Finance users had removable storage disabled to reduce the risk of data exfiltration.

All GPOs were linked at the Organizational Unit level and applied using security filtering by group, following the practice of avoiding direct GPO assignment to individual objects.
