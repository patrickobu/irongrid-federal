🏭⚡ IronGrid Federal
NIST RMF High-Impact Compliance Package — Critical Infrastructure Security
![FIPS 199: HIGH](https://img.shields.io/badge/FIPS%20199-HIGH%20Impact-red)
![NIST 800-53 Rev 5](https://img.shields.io/badge/NIST%20800--53-Rev%205-blue)
![RMF](https://img.shields.io/badge/Framework-RMF-darkgreen)
![Status: In Progress](https://img.shields.io/badge/ATO%20Status-In%20Progress-orange)

---

📌 Project Overview
IronGrid Federal is a simulated, end-to-end NIST Risk Management Framework (RMF) Authorization Package for a fictional High-Impact Critical Infrastructure Information System operated by the U.S. Department of Homeland Security (DHS), Cybersecurity and Infrastructure Security Agency (CISA) Division.
This project demonstrates hands-on knowledge of:
NIST SP 800-53 Rev 5 (HIGH Baseline Security Controls)
NIST SP 800-82 Rev 3 (ICS/OT/SCADA Security)
NIST SP 800-161 Rev 1 (Supply Chain Risk Management)
NIST SP 800-137 (Continuous Monitoring)
FIPS 199 / FIPS 200 (System Categorization)
FedRAMP High Baseline alignment
Risk Management Framework (RMF) Steps 1–6

> ⚠️ **Disclaimer:** All system names, agencies, data, personnel, and scenarios in this repository are **entirely fictional** and created for educational and portfolio purposes only. This does not represent any real U.S. government system or classified information.

---

🖥️ Fictional System Profile
Field	Details
System Name	IronGrid Federal Monitoring System (IGFMS)
System Type	National Power Grid & Water Systems Monitoring Platform
Owning Agency	U.S. Department of Homeland Security (DHS) — CISA Division (fictional)
System Owner	Mr. James A. Harlow, Deputy Director of Infrastructure Assurance (fictional)
ISSO	Portfolio Author
Hosting Environment	On-Premise Federal Tier IV Data Center — Springfield, VA (fictional)
Impact Level	FIPS 199 HIGH (Confidentiality: HIGH / Integrity: HIGH / Availability: HIGH)
Operating Environment	OT/ICS/SCADA + IT Integration
Primary Frameworks	NIST RMF, NIST 800-53 Rev 5, NIST 800-82, NIST CSF 2.0
ATO Status	In Progress

---

📂 Repository Structure

```

irongrid-federal/
│
├── README.md
│
├── 01-System-Categorization/
│   ├── fips-199-categorization.md         ← FIPS 199 HIGH impact determination
│   └── system-description.md              ← Full system description & architecture
│
├── 02-System-Security-Plan/
│   ├── ssp-overview.md                    ← SSP based on NIST SP 800-18
│   ├── system-boundary.md                 ← Authorization boundary definition
│   └── data-flow-diagram.md               ← Data flows & trust zones
│
├── 03-Control-Selection/
│   ├── nist-800-53-high-baseline.md       ← HIGH baseline control families
│   ├── controls-matrix.md                 ← Full control selection matrix
│   └── ics-scada-overlays.md              ← NIST 800-82 ICS control overlays
│
├── 04-Control-Implementation/
│   ├── access-control-AC.md               ← AC family implementation
│   ├── audit-accountability-AU.md         ← AU family implementation
│   ├── incident-response-IR.md            ← IR family implementation
│   ├── system-comms-protection-SC.md      ← SC family implementation
│   └── supply-chain-risk-SR.md            ← SR family (critical for ICS/OT)
│
├── 05-Security-Assessment/
│   ├── security-assessment-plan.md        ← SAP (NIST SP 800-53A)
│   ├── security-assessment-report.md      ← SAR with findings & risk ratings
│   └── penetration-test-summary.md        ← Pentest scope, methodology & results
│
├── 06-POA&M/
│   ├── poam-tracker.md                    ← Open findings & remediation milestones
│   └── risk-scoring.md                    ← CVSS scoring & risk prioritization
│
├── 07-Authorization/
│   ├── ato-memo-template.md               ← ATO decision memo
│   ├── risk-acceptance-letter.md          ← Authorizing Official sign-off letter
│   └── authorization-boundary.md          ← In-scope & out-of-scope components
│
├── 08-Continuous-Monitoring/
│   ├── conmon-plan.md                     ← ConMon strategy (NIST SP 800-137)
│   ├── monthly-reporting-template.md      ← Monthly ISSO status report template
│   └── vulnerability-management.md        ← Patch & vulnerability tracking process
│
├── 09-Incident-Response/
│   ├── ir-plan.md                         ← IR Plan for critical infrastructure attacks
│   └── playbook-ransomware.md             ← Ransomware response playbook
│
└── 10-Supply-Chain-Risk/
    └── scrm-plan.md                       ← NIST SP 800-161 SCRM Plan

```
---

🔐 RMF Steps Covered
RMF Step	Activity	Status
Step 1	Categorize (FIPS 199 / FIPS 200)	✅ Complete
Step 2	Select Controls (NIST 800-53 Rev 5 HIGH)	✅ Complete
Step 3	Implement Controls	🔄 In Progress
Step 4	Assess Controls (SAP / SAR)	🔄 In Progress
Step 5	Authorize (ATO Memo / POAM)	🔄 In Progress
Step 6	Monitor (ConMon / Vuln Mgmt)	🔄 In Progress

---

🎯 Target Roles This Project Supports
Information System Security Officer (ISSO)
GRC Analyst
Security Control Assessor (SCA)
Cybersecurity Analyst — Federal / Critical Infrastructure

---

📚 Key References
NIST SP 800-53 Rev 5
NIST SP 800-82 Rev 3
NIST SP 800-161 Rev 1
NIST SP 800-137
FIPS 199
FedRAMP High Baseline

---

👤 Author

[patrickobu]
Cybersecurity Professional | ISSO Candidate | GRC Analyst
🎓 CompTIA Security+ | CISSP (In Progress) | CGRC (In Progress)
www.linkedin.com/in/patrick-obu-6843181b9 | https://github.com/patrickobu

---

This repository is actively maintained and updated as part of an ongoing cybersecurity apprenticeship and professional development journey in federal RMF/GRC compliance.
