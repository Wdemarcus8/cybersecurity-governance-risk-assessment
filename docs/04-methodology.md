# Methodology

## Assessment Approach

This assessment was conducted in four phases, consistent with practices
described in NIST SP 800-30 Rev. 1 (Guide for Conducting Risk Assessments)
and structured around the NIST Cybersecurity Framework (CSF) 2.0.

### Phase 1: Scoping & Discovery
Defined the assessment boundary (systems, data, third parties) and built the
[Asset Inventory](02-asset-inventory.md). In a real-world engagement, this
phase would involve stakeholder interviews, documentation review (policies,
network diagrams, vendor contracts), and tooling review. For this fictional
case study, this information was defined as part of the company scenario
design rather than collected from a live organization.

### Phase 2: Gap Assessment
Evaluated current-state security practices against NIST CSF 2.0 Categories
and Subcategories across all six Functions (Govern, Identify, Protect,
Detect, Respond, Recover). Each Subcategory reviewed was assigned a maturity
rating (Not Implemented, Partially Implemented, Implemented, or Managed &
Measured), and gaps were flagged where current state fell short of an
"Implemented" or better rating for a control relevant to Meridian Pay's risk
profile. Full results are in the [NIST CSF Gap Assessment](03-nist-csf-gap-assessment.md).

### Phase 3: Risk Identification & Scoring
Each gap identified in Phase 2 was translated into a discrete risk statement.
Risks were scored using a **Likelihood × Impact** model on a 1–5 scale for
each dimension, consistent with NIST SP 800-30 guidance, producing a
composite risk score used to assign an overall rating (Critical / High /
Medium / Low). Closely related findings sharing a common root cause were
consolidated into single risk entries to avoid duplicative tracking. Results
are documented in the [Risk Register](../data/risk-register.xlsx).

**Likelihood Scale (1–5):** considers threat source motivation/capability and
existing control effectiveness.
**Impact Scale (1–5):** considers confidentiality, integrity, and availability
impact, plus regulatory/financial/reputational consequence given Meridian
Pay's status as a payment processor handling regulated data.

### Phase 4: Remediation Planning
For each risk in the register, a remediation action, owner, target completion
date, and status were defined and tracked in the
[POA&M](../data/poam.xlsx) (Plan of Action & Milestones), prioritized by risk
rating.

## Limitations

This is a fictional case study built for portfolio demonstration purposes.
Findings, risk scores, and the company profile were constructed to be
realistic and internally consistent, but are not derived from a live
organization, real interviews, or actual technical testing (e.g., no actual
vulnerability scanning or penetration testing was performed). In a live
engagement, findings would be substantiated with evidence (screenshots,
configuration exports, interview notes, scan results) rather than asserted.

## References

- National Institute of Standards and Technology. *Cybersecurity Framework
  (CSF) 2.0*. https://www.nist.gov/cyberframework
- National Institute of Standards and Technology. *SP 800-30 Rev. 1: Guide
  for Conducting Risk Assessments*. https://csrc.nist.gov/pubs/sp/800/30/r1/final

---

*Back to: [README](../README.md)*
