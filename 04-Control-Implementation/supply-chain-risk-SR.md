Supply Chain Risk Management (SR) — Control Implementation
IronGrid Federal Monitoring System (IGFMS)
Document Type: Control Implementation Statement
Control Family: Supply Chain Risk Management (SR)
Version: 1.0
Classification: UNCLASSIFIED // FOR OFFICIAL USE ONLY (FOUO) (fictional)
Date: January 2025
Reference: NIST SP 800-53 Rev 5 — SR Control Family | NIST SP 800-161 Rev 1
---
1. Overview
Supply chain risk management is a priority security concern for IGFMS due to the potential for adversaries to compromise national critical infrastructure monitoring capability through hardware implants, firmware backdoors, or counterfeit components introduced during the manufacturing and delivery process. This document describes IGFMS implementation of the SR control family.
---
2. SR-2 — Supply Chain Risk Management Plan
Implementation
The IGFMS Supply Chain Risk Management Plan (SCRM Plan) is maintained in `10-Supply-Chain-Risk/scrm-plan.md`. The plan is reviewed annually and updated following any supply chain security incident. It covers vendor assessment procedures, component integrity verification, delivery controls, ongoing monitoring, and supply chain incident response.
---
3. SR-3 — Supply Chain Controls and Plans
Implementation
IGFMS procurement contracts for all OT and IT components include mandatory supply chain security clauses:
Required contract clauses:
Vendor must disclose all sub-suppliers providing components used in IGFMS deliverables
Vendor must provide a Software Bill of Materials (SBOM) for all software and firmware
Vendor must notify IGFMS within 24 hours of any confirmed supply chain security incident affecting delivered components
Right-to-audit clause permitting IGFMS security personnel to assess vendor security practices
Prohibition on manufacturing in countries identified as foreign adversaries per federal acquisition regulations
Counterfeit prevention and detection requirements per SAE AS5553
Active gap: POAM-005 — Supply chain risk assessments not yet completed for 4 of 7 critical OT vendors. Vendor questionnaires sent; 3 of 4 vendors have responded.
---
4. SR-4 — Provenance
Implementation
IGFMS maintains a comprehensive component provenance record for all critical hardware and software components:
Hardware provenance tracking:
Each OT hardware component is tracked from purchase order through installation in a Configuration Management Database (CMDB)
Serial numbers verified against manufacturer records at delivery
Chain of custody documentation maintained for all OT components from manufacturer to installation
Components from non-verified sources are quarantined pending SCRM review
Software and firmware provenance:
All software and firmware versions are documented in the CMDB
Cryptographic hashes of all installed firmware images maintained and verified against vendor-provided checksums
Software version history maintained to support forensic investigation if needed
---
5. SR-6 — Supplier Assessments and Reviews
Implementation
IGFMS conducts formal supplier security assessments for all Critical and High-criticality vendors:
Assessment process:
Vendor receives IGFMS SCRM questionnaire covering 45 security domains
SCRM Manager reviews responses and identifies gaps
On-site assessment conducted for Critical vendors (annually)
Document review assessment for High vendors (annually)
Assessment report produced with risk ratings and remediation requirements
Vendor must remediate Critical findings within 90 days or face contract action
Current assessment status:
Vendor	Criticality	Last Assessed	Next Due	Status
SensorTech Corp.	Critical	Oct 2024	Oct 2025	✅ Complete
GridShield Systems	Critical	Sep 2024	Sep 2025	✅ Complete
DataDiode Inc.	Critical	Aug 2024	Aug 2025	✅ Complete
FirmwarePlus LLC	High	Not assessed	Mar 2025	🔄 POAM-005
NetCore Industrial	High	Not assessed	Mar 2025	🔄 POAM-005
SensorLink Corp.	High	Not assessed	Mar 2025	🔄 POAM-005
PowerMonitor Ltd.	High	Not assessed	Mar 2025	🔄 POAM-005
---
6. SR-9 — Tamper Resistance and Detection
Implementation
IGFMS employs multiple tamper resistance and detection measures for OT hardware components:
Physical tamper evidence:
Anti-tamper seals applied to all OT hardware enclosures at delivery
Seal integrity verified at each maintenance event
Broken or missing seals trigger immediate security incident investigation
Firmware integrity verification:
All firmware images verified via cryptographic hash before installation
Secure boot enabled on all servers verifying firmware integrity at startup
Unexpected firmware changes detected by Tripwire FIM and alerted immediately
Hardware inspection:
Physical inspection of all delivered OT hardware by security-cleared personnel
X-ray inspection available for high-value critical components on request
Incoming hardware quarantined in secure receiving area pending inspection
---
7. SR-11 — Component Authenticity
Implementation
IGFMS verifies component authenticity through multiple mechanisms:
Cryptographic verification: All firmware updates are signed by the vendor using code signing certificates. IGFMS verifies signatures before applying any firmware update. Updates with invalid or missing signatures are rejected and reported to the ISSO.
Part number and serial verification: All delivered components are verified against purchase orders. Serial numbers are validated with the manufacturer. Any discrepancy triggers a hold on the component and notification to the SCRM Manager.
Anti-counterfeiting: IGFMS procures OT components exclusively through manufacturer-authorized distributors. Gray market or surplus market components are strictly prohibited. Components of uncertain provenance are destroyed following NIST SP 800-88 procedures.
---
8. Control Implementation Summary
Control	Status	Notes
SR-1 Policy	✅ Implemented	SCRM policy approved Jan 2025
SR-2 SCRM Plan	✅ Implemented	Plan current — see 10-Supply-Chain-Risk/
SR-3 Supply Chain Controls	🔄 Partial	POAM-005 — 4 vendor assessments outstanding
SR-4 Provenance	✅ Implemented	CMDB with full component tracking
SR-5 Acquisition Strategies	✅ Implemented	Authorized distributors only
SR-6 Supplier Assessments	🔄 Partial	POAM-005 — 4 assessments pending
SR-7 Supply Chain OpSec	✅ Implemented	OpSec controls for procurement
SR-8 Notification Agreements	🔄 Partial	Clauses being added to 4 contracts
SR-9 Tamper Resistance	✅ Implemented	Anti-tamper seals + FIM
SR-10 Inspection	✅ Implemented	Physical inspection on delivery
SR-11 Component Authenticity	✅ Implemented	Cryptographic verification + authorized distributors
SR-12 Component Disposal	⏳ Planned	Formal disposal procedures in development
