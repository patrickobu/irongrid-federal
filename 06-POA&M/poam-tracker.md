Plan of Action & Milestones (POA&M)
IronGrid Federal Monitoring System (IGFMS)
Document Type: POA&M Tracker  
Version: 1.2  
Classification: UNCLASSIFIED // FOR OFFICIAL USE ONLY (FOUO) (fictional)  
Reporting Period: Q1 2025  
Prepared By: ISSO, IronGrid Federal Program Office (fictional)  
Last Updated: January 2025
---
1. Purpose
This Plan of Action & Milestones (POA&M) documents all known security weaknesses, deficiencies, and vulnerabilities identified in the IronGrid Federal Monitoring System (IGFMS) through security assessments, vulnerability scans, audits, and continuous monitoring activities.
Each item tracks:
The identified weakness
Associated NIST SP 800-53 Rev 5 control(s)
Risk rating (Critical / High / Moderate / Low)
Responsible party
Scheduled completion date
Current remediation status
---
2. POA&M Summary Dashboard
Severity	Open	In Progress	Closed This Period	Total
Critical	1	2	0	3
High	3	2	1	6
Moderate	4	5	3	12
Low	2	3	5	10
Total	10	12	9	31
---
3. Active POA&M Items
---
POA&M-001 | CRITICAL | OPEN
Field	Details
ID	IGFMS-POAM-001
Weakness	Firmware on 847 legacy SCADA sensors across 12 substations running end-of-life firmware (v2.1.x) with known remote code execution vulnerability (CVE-2024-XXXXX)
Control(s)	SI-2 (Flaw Remediation), SA-22 (Unsupported System Components), SR-11 (Component Authenticity)
Source	Vulnerability Scan — Tenable.sc (November 2024)
Risk Rating	CRITICAL — CVSS v3.1: 9.8
System Impact	An adversary could exploit this vulnerability to gain unauthenticated remote code execution on SCADA controllers, potentially manipulating power grid operations
Responsible Party	OT Systems Administrator / Vendor (SensorTech Corp.) (fictional)
Scheduled Completion	March 31, 2025
Status	OPEN — Vendor patch testing in isolated lab environment
Milestones	(1) Vendor patch validated in lab — Jan 15, 2025 ✅ / (2) Staged deployment to 10% of sensors — Feb 15, 2025 🔄 / (3) Full deployment complete — Mar 31, 2025 ⏳
Compensating Controls	Network segmentation enforced; IDS signatures deployed; 24/7 monitoring increased on affected segments
---
POA&M-002 | CRITICAL | IN PROGRESS
Field	Details
ID	IGFMS-POAM-002
Weakness	Multi-Factor Authentication (MFA) not enforced for 23 privileged administrator accounts accessing the IGFMS Core Processing Engine
Control(s)	IA-2 (Identification and Authentication), IA-2(1) (MFA for Privileged Accounts), AC-2 (Account Management)
Source	Security Control Assessment — October 2024
Risk Rating	CRITICAL — CVSS v3.1: 9.1
System Impact	Privileged accounts without MFA are susceptible to credential theft and account takeover, enabling unauthorized administrative access to the most sensitive system components
Responsible Party	Identity & Access Management Team / ISSO
Scheduled Completion	February 28, 2025
Status	IN PROGRESS — PIV card enrollment underway for 18 of 23 accounts
Milestones	(1) IAM policy updated — Nov 2024 ✅ / (2) PIV cards issued to 18 admins — Jan 2025 ✅ / (3) Remaining 5 accounts (contractors) — Feb 28, 2025 🔄
Compensating Controls	Enhanced logging on all privileged sessions; session timeouts reduced to 15 minutes; privileged access workstations (PAWs) enforced
---
POA&M-003 | CRITICAL | IN PROGRESS
Field	Details
ID	IGFMS-POAM-003
Weakness	Incident Response Plan (IRP) has not been tested via a full-scale tabletop exercise in 18 months, exceeding the required annual testing cadence
Control(s)	IR-3 (Incident Response Testing), IR-3(2) (Coordination with Related Plans), IR-8 (Incident Response Plan)
Source	Annual ISSO Review — September 2024
Risk Rating	CRITICAL — Non-compliance with NIST 800-53 HIGH baseline requirement
Responsible Party	ISSO / Incident Response Team Lead
Scheduled Completion	January 31, 2025
Status	IN PROGRESS — Tabletop exercise scheduled for January 28, 2025
Milestones	(1) Exercise scenario developed — Jan 5, 2025 ✅ / (2) Participants confirmed — Jan 10, 2025 ✅ / (3) Tabletop exercise conducted — Jan 28, 2025 🔄 / (4) After-Action Report complete — Jan 31, 2025 ⏳
Compensating Controls	IR team on elevated readiness; updated contact lists distributed
---
POA&M-004 | HIGH | OPEN
Field	Details
ID	IGFMS-POAM-004
Weakness	Audit logs from the Historian Database are not being forwarded to the centralized SIEM (Splunk) due to a misconfigured syslog agent, creating a 90-day gap in log coverage
Control(s)	AU-2 (Event Logging), AU-6 (Audit Record Review), AU-9 (Protection of Audit Information), SI-4 (System Monitoring)
Source	Continuous Monitoring Review — December 2024
Risk Rating	HIGH — CVSS v3.1: 7.5
Responsible Party	Systems Administrator / SIEM Engineer
Scheduled Completion	January 15, 2025
Status	OPEN — Configuration change ticket submitted, pending change control board (CCB) approval
Milestones	(1) CCB approval — Jan 10, 2025 🔄 / (2) Syslog reconfigured and validated — Jan 15, 2025 ⏳
Compensating Controls	Manual log review of Historian DB performed weekly; local log retention increased to 180 days
---
POA&M-005 | HIGH | OPEN
Field	Details
ID	IGFMS-POAM-005
Weakness	Supply chain risk assessments have not been completed for 4 of 7 critical third-party hardware vendors supplying OT components to IGFMS
Control(s)	SR-3 (Supply Chain Controls and Plans), SR-6 (Supplier Assessments and Reviews), SR-8 (Notification Agreements)
Source	Annual SCRM Review — October 2024
Risk Rating	HIGH
Responsible Party	Supply Chain Risk Manager / Contracting Officer
Scheduled Completion	March 15, 2025
Status	OPEN — Vendor questionnaires sent; 2 of 4 vendors responded
Milestones	(1) Vendor questionnaires sent — Nov 2024 ✅ / (2) 4 assessments complete — Feb 28, 2025 🔄 / (3) Risk findings documented in SCRM Plan — Mar 15, 2025 ⏳
Compensating Controls	Increased physical inspection of hardware deliveries; SBOM (Software Bill of Materials) requested from all vendors
---
POA&M-006 | HIGH | OPEN
Field	Details
ID	IGFMS-POAM-006
Weakness	12 user accounts belonging to former CISA contractors remain active in the IGFMS directory more than 30 days after contract termination
Control(s)	AC-2 (Account Management), AC-2(3) (Disable Accounts), PS-4 (Personnel Termination)
Source	Access Control Audit — November 2024
Risk Rating	HIGH — CVSS v3.1: 8.1
Responsible Party	IAM Team / Human Resources
Scheduled Completion	January 10, 2025
Status	OPEN — Accounts identified; pending HR confirmation of termination dates
Milestones	(1) Accounts suspended pending review — Dec 2024 ✅ / (2) HR confirmation received — Jan 7, 2025 🔄 / (3) Accounts permanently disabled/removed — Jan 10, 2025 ⏳
Compensating Controls	All 12 accounts suspended (not deleted) pending confirmation; privileged access revoked immediately
---
4. Recently Closed POA&M Items
ID	Weakness Summary	Control	Severity	Closed Date
IGFMS-POAM-007	Outdated TLS 1.0/1.1 protocols enabled on analyst dashboard	SC-8, SC-23	High	Dec 15, 2024
IGFMS-POAM-008	Missing security headers on internal web application	SI-10, SC-28	Moderate	Dec 20, 2024
IGFMS-POAM-009	Annual security awareness training overdue for 34 users	AT-2, AT-3	Moderate	Jan 5, 2025
---
5. Risk Scoring Reference
Rating	CVSS Score	Description
Critical	9.0 – 10.0	Immediate threat; exploitable with catastrophic impact
High	7.0 – 8.9	Significant risk; exploitable with major impact
Moderate	4.0 – 6.9	Moderate risk; requires remediation within 90 days
Low	0.1 – 3.9	Low risk; remediate within 180 days
---
6. POA&M Review Schedule
Activity	Frequency	Responsible
POA&M status update	Monthly	ISSO
POA&M submission to AO	Quarterly	ISSO / ISSM
Critical/High item escalation	As needed (within 48 hrs of identification)	ISSO
Annual POA&M comprehensive review	Annually	ISSM / AO
