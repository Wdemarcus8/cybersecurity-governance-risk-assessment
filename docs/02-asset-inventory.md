# Asset Inventory

**Organization:** Meridian Pay Solutions
**Purpose:** Identify and classify the systems, applications, data, and
third-party dependencies in scope for this assessment, per NIST CSF 2.0
**IDENTIFY (ID)** Function — specifically ID.AM (Asset Management).

---

## 1. Data Assets

| Data Type | Classification | Description | Regulatory Relevance |
|---|---|---|---|
| Cardholder Data (tokenized) | Restricted | Tokenized PANs and transaction metadata; full PAN never stored at rest | PCI-DSS |
| Merchant PII | Restricted | Business owner names, SSNs/EINs, bank account details for payouts | GLBA, State breach laws |
| Customer Transaction Data | Confidential | Transaction history, amounts, timestamps, merchant associations | PCI-DSS, GLBA |
| Employee PII/HR Data | Confidential | Employee records, payroll data, benefits information | State breach laws |
| Authentication Credentials | Restricted | Password hashes, MFA seeds, API keys/secrets | N/A (internal control) |
| Application/Audit Logs | Internal | System logs, access logs, CloudTrail logs | PCI-DSS (audit requirements) |
| Marketing/Public Data | Public | Website content, marketing materials | N/A |

## 2. Application & System Assets

| Asset | Type | Description | Data Handled | Criticality |
|---|---|---|---|---|
| Merchant Web Dashboard | Web Application | Customer-facing portal for transaction management, reporting | Transaction data, Merchant PII | Critical |
| Merchant Mobile App (iOS/Android) | Mobile Application | Mobile access to dashboard and POS functions | Transaction data, Merchant PII | Critical |
| Payment Processing API | Backend Service | Core service handling transaction authorization/routing | Tokenized cardholder data, Transaction data | Critical |
| Merchant Onboarding Service | Backend Service | KYC/identity verification during merchant signup | Merchant PII | High |
| Payout Engine | Backend Service | Calculates and initiates merchant payouts | Merchant PII, bank account data | Critical |
| Internal Admin Tools | Internal Application | Support/Ops team tooling for account management | Merchant PII, Transaction data | High |
| Corporate Email/Productivity (Google Workspace) | SaaS | Internal communication and collaboration | Employee PII, internal docs | Medium |
| HRIS/Payroll System | SaaS (3rd party) | Employee records and payroll processing | Employee PII | High |
| Identity Provider (Okta) | SaaS | Workforce SSO and MFA | Authentication credentials | Critical |

## 3. Infrastructure Assets

| Asset | Description | Environment | Criticality |
|---|---|---|---|
| AWS Production Account | Hosts production workloads (EKS, RDS/PostgreSQL, S3, Redis) | Production | Critical |
| AWS Staging Account | Pre-production testing environment | Staging | Medium |
| AWS Development Account | Developer sandbox environment | Development | Low |
| PostgreSQL Databases | Primary transactional data stores | Production | Critical |
| S3 Buckets | Log storage, backups, static assets | Production | High |
| Redis Cache Cluster | Session/caching layer | Production | Medium |
| Corporate Endpoints (Laptops) | Company-issued and limited BYOD devices (~250 total) | Corporate | High |
| Office Network (Austin HQ) | Corporate Wi-Fi/LAN | Corporate | Medium |

## 4. Third-Party / Vendor Assets

| Vendor | Service Provided | Data Access | Risk Tier |
|---|---|---|---|
| AWS | Cloud infrastructure hosting | All production data (encrypted) | Tier 1 (Critical) |
| Payment Gateway/Processor | Card network connectivity, tokenization | Cardholder data | Tier 1 (Critical) |
| Okta | Workforce identity & SSO | Authentication credentials | Tier 1 (Critical) |
| KYC/Identity Verification Vendor | Merchant identity verification during onboarding | Merchant PII | Tier 2 (High) |
| Offshore Support Contractor A | Tier 1 customer support | Limited transaction/merchant data (view-only) | Tier 2 (High) |
| Offshore Support Contractor B | Tier 1 customer support | Limited transaction/merchant data (view-only) | Tier 2 (High) |
| Payroll/HRIS Vendor | Payroll processing, benefits administration | Employee PII | Tier 2 (High) |

## 5. Asset Management Process Notes

Current state: asset inventory is maintained in a combination of AWS-native
tagging (for cloud infrastructure) and a manually updated spreadsheet (for
SaaS vendors, third-party services, and endpoint devices). There is no single
source of truth, and the spreadsheet is updated on an ad hoc basis rather than
continuously. This gap is addressed further in the
[NIST CSF Gap Assessment](03-nist-csf-gap-assessment.md) under the
**Identify (ID.AM)** category.

---

*Continue to: [NIST CSF Gap Assessment →](03-nist-csf-gap-assessment.md)*
