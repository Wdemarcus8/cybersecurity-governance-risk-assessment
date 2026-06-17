# Executive Summary

**Organization:** Meridian Pay Solutions
**Assessment Type:** Cybersecurity Governance, Risk & Compliance (GRC) Assessment
**Framework:** NIST Cybersecurity Framework (CSF) 2.0
**Assessment Period:** Q1 2026 (fictional)
**Prepared For:** Executive Leadership Team, Board Risk Committee
**Classification:** Internal — Confidential

---

## Purpose

Meridian Pay Solutions processes payment transactions and stores sensitive
financial and personal data on behalf of small-to-mid-size merchant customers.
As the company has scaled from a startup to a 250-person organization, security
governance has not kept pace with business growth. This assessment was
commissioned to evaluate the organization's current cybersecurity posture
against the NIST Cybersecurity Framework (CSF) 2.0, identify gaps, and produce
a prioritized, actionable remediation roadmap.

## Scope

The assessment covered all six NIST CSF 2.0 Functions — **Govern, Identify,
Protect, Detect, Respond, and Recover** — across Meridian Pay's production
cloud environment (AWS), core payment processing systems, customer-facing
applications, corporate IT environment, and third-party vendor relationships.
A full breakdown of in-scope systems and data is provided in the
[Asset Inventory](02-asset-inventory.md).

## Methodology

The assessment followed a structured four-phase approach: documentation review
and stakeholder interviews to establish current-state practices; mapping of
current-state practices against NIST CSF 2.0 Subcategories to identify gaps;
translation of identified gaps into discrete risks scored for likelihood and
impact per NIST SP 800-30 methodology; and development of a Plan of Action &
Milestones (POA&M) to track remediation. Full detail is available in the
[Methodology](04-methodology.md) document.

## Key Findings

Meridian Pay has established foundational security capabilities, including a
dedicated (if small) security team, MFA on critical administrative access, and
documented backup procedures. However, the assessment identified **13
significant gaps** relative to NIST CSF 2.0, concentrated in three areas:

**Governance maturity has not scaled with the business.** The organization
lacks a dedicated security leadership role (CISO or equivalent), a formal
enterprise risk management program, and a structured third-party/vendor risk
management process — all rated **High** risk given the organization's
reliance on third-party vendors with access to sensitive data.

**Detection and response capabilities are underdeveloped.** There is no
centralized security monitoring (SIEM), no tested incident response plan, and
no formal threat intelligence or vulnerability management process, leaving the
organization with limited ability to detect or respond to an active security
incident in a timely manner.

**Operational security hygiene has gaps that elevate risk in a regulated
environment.** Asset inventory is partially manual and not continuously
updated, MFA is not universally enforced across internal systems, security
awareness training is generic rather than role-based, and disaster recovery
capabilities have not been validated through testing in over 18 months.

## Risk Summary

Of the 13 risks identified and logged in the [Risk Register](../data/risk-register.xlsx):

| Risk Rating | Count | Examples |
|---|---|---|
| Critical | 2 | No centralized security monitoring (SIEM); no tested incident response plan |
| High | 6 | No formal ERM program; no vendor risk management; inconsistent MFA enforcement; no recurring vulnerability management |
| Medium | 3 | Manual asset inventory; outdated breach notification process; untested DR plan |
| Low | 2 | Informal access review cadence; generic (non-role-based) security awareness training |

The two **Critical** risks represent the most urgent exposure: in their
current state, Meridian Pay would have materially limited ability to detect a
breach in progress or to respond to one in a coordinated, timely manner — a
significant concern given the sensitivity of payment and customer data in
scope, and the regulatory reporting obligations that follow a confirmed
incident.

## Recommendations

Leadership should prioritize the following over the next two quarters,
detailed further in the [POA&M](../data/poam.xlsx):

Establish dedicated security leadership (CISO or VP of Security) with direct
accountability for the security program and a reporting line to executive
leadership or the board. Stand up centralized security monitoring and a
formal, tested incident response plan to close the most urgent detection and
response gaps. Build a structured vendor risk management program given the
organization's reliance on third parties with access to sensitive systems and
data. Formalize enterprise risk management so that security risk is tracked,
owned, and reported on consistently rather than managed ad hoc.

## Conclusion

Meridian Pay Solutions has the foundational pieces of a security program in
place, but governance, detection, and response capabilities require investment
to match the company's growth and its obligations as a handler of payment and
financial data. None of the identified gaps are unusual for a company at this
stage of growth, and all are addressable with the remediation plan outlined in
this assessment. Closing the two Critical-rated gaps should be treated as the
immediate priority.

---

*Continue to: [Asset Inventory →](02-asset-inventory.md)*
