Audit & Accountability (AU) — Control Implementation
IronGrid Federal Monitoring System (IGFMS)
Document Type: Control Implementation Statement
Control Family: Audit and Accountability (AU)
Version: 1.0
Classification: UNCLASSIFIED // FOR OFFICIAL USE ONLY (FOUO) (fictional)
Date: January 2025
Reference: NIST SP 800-53 Rev 5 — AU Control Family
---
1. Overview
Audit and accountability controls ensure that IGFMS actions can be traced to individual users and that security-relevant events are captured, protected, and reviewed. Given the critical infrastructure mission of IGFMS, comprehensive audit logging is essential for incident response, forensic analysis, and accountability of all system interactions.
---
2. AU-2 — Event Logging
Auditable Events
IGFMS captures the following event categories across all system components:
Event Category	Source Systems	Retention
Authentication events (success/failure)	All systems, CyberArk, AD	5 years
Privileged account usage	CyberArk PAM	5 years
Account management actions	Active Directory, IAM system	5 years
Configuration changes	All servers, NGFW, network devices	5 years
File integrity changes	Tripwire FIM	5 years
Network connection events	Palo Alto NGFW, IDS/IPS	5 years
OT anomaly detections	IGFMS core engine	5 years
Security alert generation	Splunk ES, Snort, Suricata	5 years
Data access events	Historian DB, analyst dashboard	5 years
System startup/shutdown	All servers	5 years
Known gap: Historian Database syslog forwarding to Splunk misconfigured since October 2024. POAM-004 active — remediation in progress. Local logs are retained and available for manual review.
---
3. AU-3 — Content of Audit Records
Implementation
Every IGFMS audit record includes the following mandatory fields per NIST SP 800-53 Rev 5:
Field	Description	Example
Timestamp	Date and time in UTC	2025-01-15T14:32:07Z
Event type	Category of event	Authentication — Privileged Login
User identity	Account name and UID	jsmith@igfms.dhs.gov / UID-4721
Source	System generating the event	IGFMS-PROD-SVR-04
Outcome	Success or failure	Success
Target	Object or resource affected	IGFMS Core Engine Admin Console
Source IP	Network address of originating session	10.44.22.15
Session ID	Unique session identifier	SES-20250115-443291
For OT-specific events, additional fields capture sensor ID, geographic location of sensor, telemetry value, and deviation threshold breached.
---
4. AU-6 — Audit Record Review
Implementation
Automated review: Splunk Enterprise Security performs continuous automated correlation of audit events against 300+ detection rules. High-confidence alerts are automatically routed to the SOC queue within seconds of event generation.
Manual review: SOC analysts conduct daily review of Splunk dashboards covering authentication anomalies, privileged access patterns, network boundary events, and configuration changes. ISSO reviews weekly summary reports.
Escalation: Any audit review finding that cannot be resolved as a known-good event within 30 minutes is escalated to an incident ticket.
---
5. AU-9 — Protection of Audit Information
Implementation
Audit logs are protected from unauthorized access, modification, and deletion through the following controls:
Access restriction: Only SOC personnel and ISSO have read access to Splunk audit data. No users have write or delete access to audit logs — Splunk is configured with write-once log storage.
Physical separation: Splunk cluster nodes are deployed on dedicated hardware physically separate from production servers and administrator workstations.
Cryptographic integrity: Log files are cryptographically hashed upon creation. Any modification of stored log data is automatically detected and alerted.
Backup: Audit logs are backed up to a separate offline storage system weekly. Backup media is encrypted with AES-256 and stored in a separate secure vault.
---
6. AU-11 — Audit Record Retention
Implementation
IGFMS retains all audit records for a minimum of 5 years in accordance with the National Archives and Records Administration (NARA) records schedule for federal cybersecurity audit data. Records older than 5 years are securely destroyed following NIST SP 800-88 media sanitization procedures.
Storage architecture:
Tier	Storage	Retention	Access Speed
Hot storage	Splunk indexers (SSD)	90 days	Immediate
Warm storage	Splunk SmartStore (object storage)	1 year	Minutes
Cold storage	Encrypted tape archive	5 years	Hours
---
7. AU-14 — Session Audit
Implementation
All privileged sessions on IGFMS are fully recorded through CyberArk Session Manager. Session recordings capture every keystroke, command, and screen state. Recordings are stored in CyberArk's encrypted vault and are accessible only to the ISSO and designated security personnel for investigation purposes.
Session recordings are reviewed for the following triggers: alerts from Splunk rules detecting suspicious privileged activity, post-incident forensic investigation, quarterly random sampling audit by ISSO, and annual privileged access program review.
---
8. Control Implementation Summary
Control	Status	Notes
AU-1 Policy	✅ Implemented	Reviewed Jan 2025
AU-2 Event Logging	🔄 Partial	POAM-004 — Historian DB gap
AU-3 Audit Content	✅ Implemented	All required fields captured
AU-4 Log Storage	✅ Implemented	80% threshold alerting active
AU-5 Logging Failure Response	✅ Implemented	15-min alert to SOC
AU-6 Audit Review	🔄 Partial	POAM-004 affects full coverage
AU-7 Log Reduction	✅ Implemented	Splunk dashboards
AU-8 Timestamps	✅ Implemented	NTP to NIST time servers
AU-9 Log Protection	✅ Implemented	Write-once, cryptographic hash
AU-10 Non-Repudiation	✅ Implemented	PKI digital signatures
AU-11 Log Retention	✅ Implemented	5-year tiered storage
AU-12 Log Generation	✅ Implemented	All systems configured
AU-14 Session Audit	✅ Implemented	CyberArk full session recording
