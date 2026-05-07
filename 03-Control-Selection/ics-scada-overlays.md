ICS/SCADA Security Overlays
IronGrid Federal Monitoring System (IGFMS)
Document Type: ICS/OT Security Control Overlays
Version: 1.0
Classification: UNCLASSIFIED // FOR OFFICIAL USE ONLY (FOUO) (fictional)
Date: January 2025
Reference: NIST SP 800-82 Rev 3 | NIST SP 800-53 Rev 5

---

1. Purpose
This document defines the ICS/SCADA-specific security control overlays applied to IGFMS beyond the standard NIST SP 800-53 Rev 5 HIGH baseline. These overlays address the unique security challenges of Operational Technology (OT) environments including availability requirements, vendor constraints, legacy systems, and safety considerations specific to critical infrastructure.

---
2. ICS Security Principles for IGFMS
Unlike traditional IT systems where Confidentiality is often the primary concern, OT/ICS environments prioritize security objectives in this order:
Safety — Physical safety of operators, public, and infrastructure
Availability — Continuous operation of monitoring functions
Integrity — Accuracy of sensor data and commands
Confidentiality — Protection of sensitive operational data
All ICS control overlays in this document reflect this prioritization.

---

3. OT-Specific Control Enhancements
3.1 Access Control Overlays
ICS-AC-3 — OT Network Access Enforcement
Standard AC-3 relies on software-based access control. For IGFMS OT segments, access enforcement is implemented at the hardware level through unidirectional data diode appliances. This eliminates the possibility of software misconfiguration creating unauthorized bidirectional communication paths. No software-only controls are accepted as the sole enforcement mechanism for OT boundary protection.
ICS-AC-17 — Remote Access Prohibition
Remote access to the OT/ICS network segment is strictly and unconditionally prohibited. Unlike the standard AC-17 control which allows remote access under defined conditions, IGFMS applies an absolute prohibition. Any maintenance requiring OT access must be performed physically on-site with two-person integrity. This policy has no exceptions and cannot be overridden without a formal policy change approved by the AO.

---

3.2 Configuration Management Overlays
ICS-CM-2 — Offline Baseline Configurations
OT system baseline configurations are maintained in offline, air-gapped storage media. Configuration changes to OT components require written approval from the AO, coordination with the equipment vendor, a change impact analysis signed by the ISSO, and validation in an isolated test environment before production deployment.
ICS-CM-3 — OT Change Control
All changes to OT systems undergo an enhanced change control process that includes assessment of potential operational disruptions, vendor notification and approval where required by maintenance agreements, a testing phase in the isolated OT lab environment, and a defined rollback procedure validated before implementation begins.

---

3.3 Incident Response Overlays
ICS-IR-4 — OT Incident Handling Procedures
When an incident affects or potentially affects OT components, IGFMS IR procedures include OT-specific steps not present in standard IR-4. These include immediate notification to field operators to activate safe mode on affected systems, engagement of the OT vendor hotline for critical equipment, coordination with DOE and EPA liaisons regarding potential operational impacts, and physical inspection of all affected OT hardware before reconnection.

---

3.4 Maintenance Overlays
ICS-MA-3 — OT Maintenance Tool Controls
All tools, test equipment, and diagnostic software used for OT system maintenance are physically inspected before use to prevent introduction of malware or unauthorized modifications. Maintenance tools are stored in a controlled access cabinet with logged access. Software-based diagnostic tools are validated against known-good cryptographic hashes before each use.
ICS-MA-5 — OT Maintenance Personnel
Personnel performing maintenance on OT components must hold appropriate security clearances and have completed OT-specific security awareness training. Third-party vendor maintenance personnel must be escorted by an authorized IGFMS employee at all times and are prohibited from connecting personal devices to any OT system component.

---

3.5 Physical Protection Overlays
ICS-PE-3 — Two-Person Integrity for OT Controllers
Physical access to SCADA controllers and OT network equipment requires two authorized personnel to be present simultaneously. This two-person integrity rule prevents unauthorized or accidental modifications by a single individual and ensures a second pair of eyes on all physical OT maintenance activities.

---

3.6 System Integrity Overlays
ICS-SA-22 — Unsupported OT Components
IGFMS tracks all OT components with end-of-life firmware or software. POAM-001 documents the 847 legacy SCADA sensors with EOL firmware. For unsupported components that cannot be immediately replaced, compensating controls include enhanced network segmentation, increased monitoring, and formal risk acceptance by the AO with a defined remediation timeline.
ICS-SI-2 — OT Patch Management
OT patching follows a specialized process distinct from IT patch management. All OT patches must be validated by the equipment vendor before application. Patches are tested in the isolated OT lab environment for a minimum of 72 hours before production deployment. Patch deployment requires a scheduled maintenance window coordinated with field operators and approved by the AO. For patches that cannot be applied without operational downtime, a formal risk acceptance memo is required.
ICS-SI-4 — Passive OT Monitoring Only
Active network scanning of OT components is strictly prohibited as active scanning can disrupt real-time control systems and cause operational failures. All OT vulnerability monitoring is performed using passive monitoring tools (Claroty) that analyze existing network traffic without injecting scan packets. Vulnerability data is supplemented by vendor advisories and ICS-CERT alerts.

---

4. Availability-First Security Decisions
The following decisions document where IGFMS has accepted additional security risk in favor of maintaining OT availability, with compensating controls in place:
Decision	Risk Accepted	Compensating Control	AO Approval
OT patches require 72-hour lab testing before production	Delayed patch deployment	Enhanced monitoring, network isolation	Required per case
Legacy SCADA firmware (POAM-001) — phased replacement over 90 days	Known RCE vulnerability present	Network segmentation, IDS signatures, 24/7 monitoring	Documented in POAM-001
No active OT scanning	Delayed vulnerability discovery	Passive Claroty monitoring + vendor advisories	Standing approval
Two-person maintenance rule may delay emergency response	Longer response time	Pre-authorized emergency procedures documented	AO approved emergency procedure

---

5. ICS Security References
NIST SP 800-82 Rev 3 — Guide to Operational Technology (OT) Security
ICS-CERT Advisories — cisa.gov/ics-advisories
NERC CIP Standards — Critical Infrastructure Protection
ISA/IEC 62443 — Security for Industrial Automation and Control Systems
CISA Cross-Sector Cybersecurity Performance Goals
