Continuous Monitoring Plan
IronGrid Federal Monitoring System (IGFMS)
Document Type: Continuous Monitoring (ConMon) Strategy  
Version: 1.1  
Classification: UNCLASSIFIED // FOR OFFICIAL USE ONLY (FOUO) (fictional)  
Date: 2025  
Prepared By: ISSO, IronGrid Federal Program Office (fictional)  
Reference: NIST SP 800-137, NIST SP 800-53 Rev 5 (CA-7), OMB Memorandum M-14-03
---
1. Purpose
This Continuous Monitoring (ConMon) Plan establishes the strategy, processes, and schedule for ongoing monitoring of the security posture of the IronGrid Federal Monitoring System (IGFMS). It ensures that security controls remain effective over time and that risks are identified and remediated in a timely manner, maintaining the system's Authority to Operate (ATO).
---
2. ConMon Strategy Overview
IGFMS implements a risk-based, tiered continuous monitoring program aligned with NIST SP 800-137. Given the system's FIPS 199 HIGH impact level and its role in protecting national critical infrastructure, IGFMS maintains one of the most rigorous ConMon programs in the federal enterprise.
2.1 ConMon Objectives
Maintain ongoing situational awareness of IGFMS security posture
Ensure security controls remain implemented correctly and operating as intended
Identify vulnerabilities, misconfigurations, and deviations from baseline promptly
Enable risk-informed decisions by the Authorizing Official (AO)
Support timely POA&M updates and remediation tracking
Provide monthly security status reporting to the AO and ISSM
---
3. Monitoring Activities & Frequencies
3.1 Continuous (Real-Time / Daily)
Activity	Tool / Method	Owner
Security event monitoring & alerting	Splunk Enterprise Security (SIEM)	SOC / ISSO
IDS/IPS signature alerting	Snort + Suricata (OT segment)	SOC
Privileged account session monitoring	CyberArk PAM	IAM Team
Data diode integrity monitoring	Hardware health checks	OT Admins
OT sensor anomaly detection	IGFMS Core Engine	CISA Analysts
File integrity monitoring (FIM)	Tripwire	Systems Admin
Firewall rule change alerting	Palo Alto NGFW	Network Team
3.2 Weekly
Activity	Tool / Method	Owner
Vulnerability scan (IT segment)	Tenable.sc	Security Team
Review of SIEM alert trends & false positives	Splunk dashboards	ISSO
Patch status review	SCCM / WSUS	Systems Admin
Review of privileged account activity logs	CyberArk reports	IAM Team
Physical security log review	Data center access logs	Facility Security
3.3 Monthly
Activity	Tool / Method	Owner
Vulnerability scan (OT/ICS segment)	Claroty / Dragos (passive)	OT Security Team
POA&M status update	Manual / GRC tool	ISSO
Security metrics report to AO	Monthly ConMon Report	ISSO / ISSM
Account recertification review	IAM system	ISSO / IAM Team
Configuration baseline comparison	SCAP / STIG compliance tool	Systems Admin
Threat intelligence review	AIS, E-ISAC, WaterISAC feeds	Threat Intel Analyst
Change management review	CCB meeting minutes	Change Manager
3.4 Quarterly
Activity	Tool / Method	Owner
Security control assessment (subset)	Manual assessment / SCA	SCA / ISSO
POA&M submission to Authorizing Official	Formal POA&M report	ISSO / ISSM
Penetration test (targeted, scoped)	Third-party / Red Team	Security Assessor
Supply chain risk review	SCRM tracker	SCRM Manager
Contingency plan test (tabletop or functional)	Tabletop exercise	ISSO / IR Team
Privacy impact review	PIA checklist	Privacy Officer
3.5 Annually
Activity	Tool / Method	Owner
Full security control assessment	NIST 800-53A methodology	Independent SCA
Penetration test (full scope, red team)	Third-party Red Team	External Assessor
Security Assessment Report (SAR) update	Formal SAR document	SCA / ISSO
ATO renewal review	AO decision	AO / ISSM / ISSO
System Security Plan (SSP) review & update	SSP document	ISSO
Incident Response Plan (IRP) tabletop	Full-scale tabletop exercise	IR Team / ISSO
Privacy Threshold Analysis (PTA) update	PTA document	Privacy Officer
Disaster Recovery / COOP test	DR exercise	IT Operations
---
4. Security Metrics
The following key security metrics are tracked and reported monthly to the AO:
Metric	Target	Reporting Frequency
Critical vulnerabilities unpatched > 15 days	0	Monthly
High vulnerabilities unpatched > 30 days	0	Monthly
Open Critical/High POA&M items	< 5	Monthly
MFA enforcement rate (privileged accounts)	100%	Monthly
Patch compliance rate (IT systems)	≥ 98%	Monthly
STIG compliance score	≥ 90%	Monthly
Mean Time to Detect (MTTD) security incidents	< 1 hour	Monthly
Mean Time to Respond (MTTR) to critical incidents	< 4 hours	Monthly
User security awareness training completion	100%	Quarterly
Unauthorized configuration changes detected	0	Monthly
---
5. Vulnerability Management
5.1 Scan Schedule
Segment	Tool	Frequency	Method
IT Network	Tenable.sc	Weekly	Authenticated scan
OT/ICS Network	Claroty / Dragos	Monthly	Passive (non-intrusive)
Web Applications	OWASP ZAP + Burp Suite	Quarterly	Active scan
Database	DbProtect	Monthly	Authenticated scan
5.2 Remediation SLAs
Severity	Patch SLA
Critical (CVSS 9.0–10.0)	15 calendar days
High (CVSS 7.0–8.9)	30 calendar days
Moderate (CVSS 4.0–6.9)	90 calendar days
Low (CVSS 0.1–3.9)	180 calendar days
> **OT Exception:** For OT/ICS systems where patching requires operational downtime, a risk acceptance memo signed by the AO is required along with compensating controls documentation.
---
6. Configuration Management Monitoring
All IT systems must comply with applicable DISA STIGs and CIS Benchmarks
SCAP-compliant scanning performed monthly; deviations tracked in POA&M
All configuration changes must go through the Change Control Board (CCB) process
Unauthorized configuration changes detected via FIM trigger immediate security incident response
---
7. Reporting
7.1 Monthly ConMon Report Contents
Each monthly report submitted to the AO and ISSM includes:
Executive summary of security posture
Vulnerability scan results and trending
POA&M status update (new, in-progress, closed items)
Security metrics dashboard (vs. targets)
Significant security events or incidents
Patch compliance status
Upcoming assessment activities
Risk recommendations
7.2 Distribution
Report	Recipients	Frequency
Monthly ConMon Report	AO, ISSM, ISSO, System Owner	Monthly
Quarterly POA&M	AO, ISSM	Quarterly
Annual SAR	AO, ISSM, Program Office	Annually
Incident Reports	AO, ISSM, US-CERT	As needed
---
8. Roles & Responsibilities
Role	ConMon Responsibilities
ISSO	Owns ConMon program; prepares monthly reports; updates POA&M; coordinates assessments
ISSM	Reviews and approves monthly reports; escalates to AO; oversees ISSO activities
Authorizing Official (AO)	Reviews monthly reports; approves risk acceptances; makes ATO decisions
SOC / Security Operations	24/7 monitoring; incident detection and initial response
Systems Administrators	Patch management; configuration compliance; FIM management
OT Security Team	OT/ICS vulnerability management; ICS-specific monitoring
IAM Team	Account lifecycle management; privileged access monitoring
---
9. References
NIST SP 800-137 — Information Security Continuous Monitoring (ISCM)
NIST SP 800-53 Rev 5 — CA-7 (Continuous Monitoring)
OMB Memorandum M-14-03 — Enhancing the Security of Federal Networks
CISA Continuous Diagnostics and Mitigation (CDM) Program
NIST SP 800-82 Rev 3 — OT/ICS ConMon considerations
