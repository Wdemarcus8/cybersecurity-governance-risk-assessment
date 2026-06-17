# NIST CSF 2.0 Gap Assessment

**Organization:** Meridian Pay Solutions
**Framework Version:** NIST Cybersecurity Framework (CSF) 2.0
**Assessment Approach:** For each of the six CSF Functions, current-state
practices were evaluated against representative Categories and Subcategories.
Each finding is rated by maturity tier and, where a gap exists, carried
forward into the [Risk Register](../data/risk-register.xlsx) for scoring.

**Maturity Rating Scale:**

| Rating | Description |
|---|---|
| Not Implemented | No process or control exists |
| Partially Implemented | Process exists but is informal, inconsistent, or incomplete |
| Implemented | Process is formalized and operating, but not yet measured/optimized |
| Managed & Measured | Process is formalized, consistently operating, and tracked with metrics |

---

## 1. GOVERN (GV)

The Govern function establishes and monitors the organization's cybersecurity
risk management strategy, expectations, and policy.

| Category | Subcategory (representative) | Current State | Maturity | Gap Identified |
|---|---|---|---|---|
| Organizational Context (GV.OC) | GV.OC-01: Organizational mission is understood and informs cybersecurity risk management | Security priorities are generally understood by leadership but not formally documented as risk appetite/tolerance statements | Partially Implemented | Yes — no formal risk appetite statement |
| Risk Management Strategy (GV.RM) | GV.RM-01: Risk management objectives are established and agreed by organizational stakeholders | No formal enterprise risk management (ERM) program; security risks tracked ad hoc by the security team without cross-functional risk committee oversight | Not Implemented | **Yes — Critical/High** |
| Roles, Responsibilities & Authorities (GV.RO) | GV.RO-01: Organizational leadership is responsible and accountable for cybersecurity risk | No dedicated CISO or equivalent security executive; security team reports to CTO with no direct board/executive risk reporting line | Partially Implemented | **Yes — High** |
| Policy (GV.PO) | GV.PO-01: Policy for managing cybersecurity risks is established | InfoSec policy exists but has not been reviewed or updated in 3 years | Partially Implemented | Yes — Medium |
| Oversight (GV.OV) | GV.OV-01: Cybersecurity risk management strategy outcomes are reviewed | No regular (e.g., quarterly) security posture reporting to executive leadership or board | Not Implemented | Yes — Medium |
| Cybersecurity Supply Chain Risk Management (GV.SC) | GV.SC-01: Supply chain risk management processes are established | No formal vendor security risk assessment process; vendor contracts reviewed by legal only, not security | Not Implemented | **Yes — High** |

## 2. IDENTIFY (ID)

The Identify function helps determine the current cybersecurity risk to the
organization's systems, assets, data, and capabilities.

| Category | Subcategory (representative) | Current State | Maturity | Gap Identified |
|---|---|---|---|---|
| Asset Management (ID.AM) | ID.AM-01: Inventories of hardware managed by the organization are maintained | Asset inventory exists but is partially manual (spreadsheet) and not continuously updated | Partially Implemented | Yes — Medium |
| Asset Management (ID.AM) | ID.AM-07: Inventories of data and corresponding metadata are maintained | Data classification exists informally but is not documented in a formal data inventory/map | Partially Implemented | Yes — Medium |
| Risk Assessment (ID.RA) | ID.RA-01: Vulnerabilities in assets are identified and documented | No formal, recurring vulnerability management program; scanning is ad hoc | Partially Implemented | **Yes — High** |
| Risk Assessment (ID.RA) | ID.RA-05: Threats, vulnerabilities, likelihood, and impact are used to determine risk | No documented risk scoring methodology prior to this assessment | Not Implemented | Yes — Medium (addressed by this project) |
| Improvement (ID.IM) | ID.IM-01: Improvements are identified from evaluations | No formal post-assessment or post-incident lessons-learned process | Not Implemented | Yes — Low |

## 3. PROTECT (PR)

The Protect function supports the organization's ability to use safeguards to
prevent or reduce cybersecurity risk.

| Category | Subcategory (representative) | Current State | Maturity | Gap Identified |
|---|---|---|---|---|
| Identity Management, Authentication & Access Control (PR.AA) | PR.AA-03: Users, services, and hardware are authenticated | MFA enforced for AWS root/admin and Okta SSO, but not universally required for all internal systems | Partially Implemented | **Yes — High** |
| Identity Management, Authentication & Access Control (PR.AA) | PR.AA-05: Access permissions are defined and enforced incorporating least privilege | Role-based access exists for core systems, but periodic access reviews are not formally scheduled | Partially Implemented | Yes — Medium |
| Awareness & Training (PR.AT) | PR.AT-01: Personnel are provided awareness and training | Annual security awareness training exists but is generic, not role-based (e.g., engineers and support staff receive the same content) | Partially Implemented | Yes — Medium |
| Data Security (PR.DS) | PR.DS-01: Data-at-rest is protected | Production databases and S3 buckets are encrypted at rest | Implemented | No |
| Data Security (PR.DS) | PR.DS-02: Data-in-transit is protected | TLS enforced for external traffic; internal service-to-service encryption inconsistent | Partially Implemented | Yes — Medium |
| Platform Security (PR.PS) | PR.PS-01: Configuration management practices are established | Infrastructure-as-code used for most production deployments, but configuration drift is not actively monitored | Partially Implemented | Yes — Low |

## 4. DETECT (DE)

The Detect function supports timely discovery of cybersecurity attacks and
compromises.

| Category | Subcategory (representative) | Current State | Maturity | Gap Identified |
|---|---|---|---|---|
| Continuous Monitoring (DE.CM) | DE.CM-01: Networks and network services are monitored | Logging exists (CloudTrail, application logs) but there is no centralized SIEM correlating events across systems | Not Implemented | **Yes — Critical** |
| Continuous Monitoring (DE.CM) | DE.CM-03: Personnel activity is monitored to find potentially adverse events | No automated alerting on anomalous access patterns or privileged account activity | Not Implemented | **Yes — High** |
| Adverse Event Analysis (DE.AE) | DE.AE-02: Potentially adverse events are analyzed | No formal SOC process or defined detection use cases; alert triage is ad hoc when logs are reviewed manually | Not Implemented | **Yes — Critical** |

## 5. RESPOND (RS)

The Respond function supports taking action regarding a detected cybersecurity
incident.

| Category | Subcategory (representative) | Current State | Maturity | Gap Identified |
|---|---|---|---|---|
| Incident Management (RS.MA) | RS.MA-01: The incident response plan is executed once an incident is declared | No formal, documented incident response plan exists | Not Implemented | **Yes — Critical** |
| Incident Management (RS.MA) | RS.MA-02: Incidents are categorized and prioritized | No defined incident severity/classification scheme | Not Implemented | Yes — High |
| Incident Analysis (RS.AN) | RS.AN-03: Analysis is performed to establish what has taken place during an incident, and the root cause | No forensic readiness procedures (e.g., evidence preservation steps) defined | Not Implemented | Yes — Medium |
| Incident Response Reporting & Communication (RS.CO) | RS.CO-02: Internal and external stakeholders are notified of incidents | No defined breach notification procedure mapped to regulatory timelines (state breach laws, card network rules) | Not Implemented | **Yes — High** |

## 6. RECOVER (RC)

The Recover function supports timely restoration of normal operations to
reduce the effects of cybersecurity incidents.

| Category | Subcategory (representative) | Current State | Maturity | Gap Identified |
|---|---|---|---|---|
| Incident Recovery Plan Execution (RC.RP) | RC.RP-01: The recovery portion of the incident response plan is executed | Backup procedures exist for production databases, but no formal recovery plan exists separate from backup mechanics | Partially Implemented | Yes — Medium |
| Incident Recovery Plan Execution (RC.RP) | RC.RP-04: Critical mission functions and cybersecurity risk management are considered to establish post-incident operational norms | Disaster recovery plan exists but has not been tested via tabletop or live failover exercise in 18+ months | Partially Implemented | **Yes — High** |
| Incident Recovery Communication (RC.CO) | RC.CO-03: Recovery activities are communicated to stakeholders | No defined communication plan for customer/merchant notification during extended outages | Not Implemented | Yes — Medium |

---

## Summary of Gaps by Function

| Function | Gaps Identified | Critical | High | Medium | Low |
|---|---|---|---|---|---|
| Govern | 5 | 0 | 2 | 2 | 0 |
| Identify | 4 | 0 | 1 | 2 | 1 |
| Protect | 4 | 0 | 1 | 3 | 0 |
| Detect | 3 | 2 | 1 | 0 | 0 |
| Respond | 4 | 1 | 2 | 1 | 0 |
| Recover | 3 | 0 | 1 | 2 | 0 |
| **Total** | **23 findings (13 carried to Risk Register as distinct risks)*** | **3** | **8** | **10** | **1** |

*Note: Several closely related findings within the same Function were
consolidated into a single risk register entry where they share a common root
cause and remediation path (e.g., the three Detect-function gaps are
consolidated into two risk register entries: "no centralized monitoring" and
"no SOC/alert triage process"). See the [Risk Register](../data/risk-register.xlsx)
for the consolidated, scored list of 13 risks.

---

*Continue to: [Methodology →](04-methodology.md) | [Risk Register →](../data/risk-register.xlsx)*
