Access Control (AC) — Control Implementation
IronGrid Federal Monitoring System (IGFMS)
Document Type: Control Implementation Statement
Control Family: Access Control (AC)
Version: 1.0
Classification: UNCLASSIFIED // FOR OFFICIAL USE ONLY (FOUO) (fictional)
Date: January 2025
Reference: NIST SP 800-53 Rev 5 — AC Control Family
---
1. Overview
This document describes how the Access Control (AC) control family is implemented within IGFMS. Access control is foundational to IGFMS security given its role in protecting national critical infrastructure data. IGFMS enforces a strict least-privilege, role-based access control model with PIV/MFA authentication required for all users.
---
2. AC-2 — Account Management
Implementation
All IGFMS user accounts are managed through Microsoft Active Directory integrated with CyberArk Privileged Access Manager. Account lifecycle management follows a formal process from creation through termination.
Account types defined for IGFMS:
Account Type	Description	MFA Requirement	Review Frequency
Standard user	CISA analysts — read-only dashboard access	PIV + software token	Quarterly
Power user	Senior analysts — alert management	PIV + software token	Quarterly
Administrator	Systems administrators — privileged access	PIV card mandatory	Monthly
Service account	System-to-system authentication	Certificate-based	Semi-annually
Emergency account	Break-glass for disaster recovery	Dual-custody + PIV	Semi-annually
Account provisioning process:
Supervisor submits access request via IGFMS ticketing system
ISSO reviews and approves based on role justification and need-to-know
IAM team creates account with minimum necessary permissions
User completes role-specific security awareness training before first access
Account activation confirmed by ISSO
Account termination process:
HR system triggers automated termination notification to IAM team
Account suspended within 1 business day of separation notification
Account permanently disabled within 30 days following confirmation
Known gap: POAM-006 — 12 contractor accounts identified as active beyond 30-day window
Quarterly account reviews:
ISSO conducts quarterly reviews of all active accounts verifying continued need-to-know, appropriate access levels, and no dormant accounts. Review results documented and provided to ISSM.
---
3. AC-3 — Access Enforcement
Implementation
Access enforcement in IGFMS is implemented through multiple layered mechanisms:
Role-Based Access Control (RBAC): Active Directory security groups define access permissions for each system component. Permissions are assigned to groups, not individuals. Users are added to groups based on their approved role.
AD Group	System Access	Permission Level
IGFMS-Analysts	Analyst dashboard, alert review	Read-only
IGFMS-Commanders	All analyst functions + escalation	Read/write alerts
IGFMS-Admins	All system components	Full administrative
IGFMS-ISSO	Security console, audit logs	Security administrative
IGFMS-ReadOnly	Reporting portal	Read-only
Privileged Access Management: All administrative access to IGFMS servers and network infrastructure is brokered through CyberArk PAM. Administrators check out credentials for each session. Sessions are fully recorded. Credentials are automatically rotated after each checkout.
OT Network Access: The hardware data diode provides the ultimate access enforcement mechanism for the OT segment — physical hardware that makes bidirectional access technically impossible regardless of software configuration.
---
4. AC-4 — Information Flow Enforcement
Implementation
Information flow within IGFMS is governed by hardware and software controls enforcing the defined data flow policy:
Hardware enforcement (OT→IT): Waterfall Security unidirectional gateway appliances physically enforce one-way data flow from the OT/ICS sensor network to the IT processing tier. No TCP/IP return path exists.
Network segmentation: Palo Alto PA-5450 NGFW enforces inter-segment information flow policies. All traffic between network zones is inspected and controlled by application-aware firewall rules. Default-deny policy applied — only explicitly permitted flows are allowed.
Data classification enforcement: CUI data is handled only on systems approved for CUI processing. IGFMS operator workstations are CUI-approved with DLP controls preventing unauthorized exfiltration.
---
5. AC-6 — Least Privilege
Implementation
Least privilege is enforced at every layer of IGFMS:
Operating system level: All server operating systems run with minimal installed services, disabled unnecessary accounts, and non-administrative user accounts for application processes. Root/administrator access requires CyberArk checkout.
Application level: IGFMS application roles are scoped to minimum necessary functions. Analysts cannot modify system configurations. Administrators cannot view classified content. ISSO has read-only access to audit logs (cannot modify).
Just-in-time access: CyberArk PAM implements just-in-time privileged access. Administrators do not hold persistent elevated privileges. They request access for a defined purpose and duration. Sessions are automatically terminated at timeout.
Network level: NGFW rules enforce least-privilege network access. Each system can only communicate with the specific hosts and ports required for its function. East-west traffic within the data center is restricted by micro-segmentation policy.
---
6. AC-17 — Remote Access
Implementation
Remote access to IGFMS is subject to strict controls differentiated by network segment:
OT segment: Remote access is unconditionally prohibited. This is an absolute restriction with no exceptions. Any maintenance requiring physical access to OT components must be performed on-site.
IT segment: Remote access is permitted for authorized administrators and ISSO personnel only, subject to the following requirements:
PIV card authentication mandatory
VPN connection to CISA government network required
Session conducted from a government-issued, IGFMS-approved endpoint
Session proxied through CyberArk PAM — full session recording
VPN session limited to 4 hours maximum before re-authentication required
Remote access automatically logged and reviewed by ISSO weekly
Remote access monitoring: All remote sessions generate Splunk alerts reviewed by the SOC. Anomalous remote access patterns (unusual hours, unusual source locations) trigger immediate investigation.
---
7. Control Implementation Summary
Control	Status	Gap / Note
AC-1 Policy	✅ Implemented	Reviewed Jan 2025
AC-2 Account Mgmt	🔄 Partial	POAM-006 active
AC-3 Access Enforcement	✅ Implemented	RBAC + PAM active
AC-4 Info Flow	✅ Implemented	Data diode + NGFW
AC-5 Separation of Duties	✅ Implemented	Roles separated
AC-6 Least Privilege	✅ Implemented	JIT via CyberArk
AC-7 Failed Logins	✅ Implemented	5-attempt lockout
AC-8 System Banner	✅ Implemented	Warning on all systems
AC-17 Remote Access	✅ Implemented	OT prohibited; IT PAM-brokered
AC-18 Wireless	✅ Implemented	No wireless in OT
AC-19 Mobile Devices	✅ Implemented	MDM enrolled, govt-issued only
AC-20 External Systems	✅ Implemented	ISAs govern all connections
