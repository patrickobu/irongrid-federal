Supply Chain Risk Management Plan (SCRM)
IronGrid Federal Monitoring System (IGFMS)
Document Type: Supply Chain Risk Management Plan
Version: 1.0
Classification: UNCLASSIFIED // FOR OFFICIAL USE ONLY (FOUO) (fictional)
Date: January 2025
Reference: NIST SP 800-161 Rev 1 | NIST SP 800-53 Rev 5 (SR family)
---
1. Purpose
This Supply Chain Risk Management (SCRM) Plan establishes the strategy, processes, and controls for identifying, assessing, and mitigating cybersecurity risks introduced through the IGFMS supply chain. Given that IGFMS components include ICS/SCADA hardware sourced from multiple vendors and deployed in a national critical infrastructure monitoring role, supply chain integrity is a fundamental security requirement.
---
![Roles and Responsibilities Matrix](../diagrams/08-roles-matrix.png)
---
2. Supply Chain Risk Overview
IGFMS faces unique supply chain risks due to its role in critical infrastructure monitoring. Adversaries motivated to disrupt U.S. power grid and water system monitoring have strong incentives to compromise IGFMS through supply chain vectors including hardware implants in OT components, firmware backdoors introduced during manufacturing, counterfeit components substituted in the supply chain, and compromised software updates from legitimate vendors.
---
3. Critical Suppliers
Vendor	Component Supplied	Criticality	Assessment Status
SensorTech Corp. (fictional)	Primary SCADA sensor hardware	Critical	✅ Assessed — Oct 2024
GridShield Systems (fictional)	ICS firewall appliances	Critical	✅ Assessed — Sep 2024
DataDiode Inc. (fictional)	Unidirectional gateway hardware	Critical	✅ Assessed — Aug 2024
FirmwarePlus LLC (fictional)	SCADA firmware maintenance	High	🔄 Pending — POAM-005
NetCore Industrial (fictional)	OT network switches	High	🔄 Pending — POAM-005
SensorLink Corp. (fictional)	Water sensor modules	High	🔄 Pending — POAM-005
PowerMonitor Ltd. (fictional)	Power substation interface units	High	🔄 Pending — POAM-005
---
4. SCRM Controls
4.1 Procurement Controls
All IGFMS component procurement follows these mandatory requirements before contract award:
Vendor must complete SCRM questionnaire covering manufacturing locations, sub-suppliers, and quality controls
Software Bill of Materials (SBOM) required for all software and firmware components
Contractual notification requirements if vendor is acquired, sold, or experiences a supply chain security incident
FOCI (Foreign Ownership, Control, or Influence) assessment for all vendors with foreign operations
Right-to-audit clause included in all critical vendor contracts
4.2 Delivery and Receipt Controls
All hardware deliveries to IGFMS undergo the following controls:
Physical inspection of packaging for signs of tampering on delivery
Verification of anti-tamper seals on all OT hardware components
Cryptographic hash verification of all firmware images against vendor-provided checksums
Chain of custody documentation from manufacturer to installation
Serial number verification against purchase order
4.3 Ongoing Vendor Monitoring
Annual reassessment of all Critical vendors
Annual reassessment of all High vendors
Immediate reassessment triggered by: vendor acquisition, known supply chain compromise at vendor, significant change in vendor security posture
Subscription to ICS-CERT and vendor security advisories for all critical components
---
5. Software Bill of Materials (SBOM)
IGFMS maintains SBOMs for all critical software and firmware components. SBOMs are reviewed quarterly against known vulnerability databases including NVD, ICS-CERT, and vendor advisories. Any component identified as vulnerable triggers the IGFMS patch management process.
---
6. SCRM Incident Response
If a supply chain compromise is suspected or confirmed, the ISSO will initiate the following specific SCRM incident actions in addition to the standard IR plan:
Immediately quarantine all components from the affected vendor
Notify the AO and ISSM within 1 hour
Notify CISA and relevant ISACs within 2 hours
Engage the vendor's security team to obtain technical details of the compromise
Conduct a forensic review of all installed components from the affected vendor
Evaluate alternative sourcing options for replacement components
Report to relevant federal supply chain risk management bodies
---
7. Plan Review Schedule
Review	Frequency	Owner
Full SCRM plan review	Annual	SCRM Manager / ISSO
Critical vendor reassessment	Annual	SCRM Manager
SBOM vulnerability review	Quarterly	Systems Admin / ISSO
Post-incident SCRM review	As needed	ISSO
---
8. References
NIST SP 800-161 Rev 1 — Cybersecurity Supply Chain Risk Management
NIST SP 800-53 Rev 5 — SR Control Family
Executive Order 14028 — Supply Chain Security Requirements
CISA ICT Supply Chain Risk Management Task Force Guidance
NSA Supply Chain Risk Management Guidance
