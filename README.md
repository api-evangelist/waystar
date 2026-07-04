# Waystar (waystar)

Waystar is a healthcare payments and revenue cycle management (RCM) software company that operates a national clearinghouse connecting providers to payers. Its cloud platform spans financial clearance (eligibility, prior authorization, patient estimation), claim management, payment and remittance management, and denial prevention and recovery. Waystar integrates with practice management (PM), hospital information systems (HIS), and EHRs through REST APIs, web services, HL7, sFTP/batch, RPA (bots), and X12 EDI transactions.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/waystar/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/waystar/refs/heads/main/apis.yml)

## Access Model — Partner / Developer Gated

Waystar operates a developer portal at [developer.waystar.com](https://developer.waystar.com/), and its public material describes integration via "REST APIs, web services, sFTP, HL7, batch, X12 EDI, RPA (bot)" along with "HMAC Security for Web Services / API Information" and a "Credential Management API." However:

- **No public OpenAPI definition or open endpoint reference is published.** Full API specifications, base URLs, sandbox credentials, and authentication detail (HMAC-SHA256 and/or OAuth 2.0) sit behind developer-portal registration and a signed Waystar partnership/client agreement.
- The APIs documented in this repository are therefore **modeled** from Waystar's public product pages, developer-portal descriptions, and the underlying **X12 EDI standards** — not confirmed from a published machine-readable spec. Endpoint paths and base URLs are intentionally omitted rather than fabricated.
- Access is obtained by becoming a Waystar client or technology partner via [waystar.com/clients-partners](https://www.waystar.com/clients-partners/).

This is an **honest gated stub**: the provider is real and does expose programmatic integration, but the concrete API surface is not publicly documented.

## X12 EDI Transaction Coverage

Waystar's clearinghouse is built on the standard HIPAA X12 transaction sets, which is what the modeled APIs map to:

- **270 / 271** — Eligibility and benefit inquiry / response
- **276 / 277** — Claim status inquiry / response
- **278** — Health care services review (prior authorization / referral)
- **837P / 837I / 837D** — Claims (professional / institutional / dental)
- **835** — Remittance advice (ERA) / electronic payment

## Tags

- Healthcare
- Revenue Cycle Management
- RCM
- Clearinghouse
- Healthcare Payments
- Medical Billing
- X12 EDI
- Eligibility
- Claims
- Remittance

## Timestamps

- **Created:** 2026-07-04
- **Modified:** 2026-07-04

## APIs (Modeled)

### Waystar Eligibility Verification API

Real-time and batch insurance eligibility and benefits verification (X12 270/271) — coverage, plan details, copays, deductibles, and service-type benefits before a visit.

- **Human URL:** [https://www.waystar.com/our-platform/financial-clearance/eligibility-verification/](https://www.waystar.com/our-platform/financial-clearance/eligibility-verification/)

### Waystar Authorization & Referral API

Prior authorization and referral determination and status (X12 278), with RPA/payer-portal automation where payers lack a transaction.

- **Human URL:** [https://www.waystar.com/our-platform/financial-clearance/authorizations/](https://www.waystar.com/our-platform/financial-clearance/authorizations/)

### Waystar Patient Estimation API

Pre-service, good-faith patient cost estimates combining eligibility/benefits, contracted rates, and procedure codes for price transparency and up-front collections.

- **Human URL:** [https://www.waystar.com/our-platform/financial-clearance/coverage-detection/](https://www.waystar.com/our-platform/financial-clearance/coverage-detection/)

### Waystar Claim Management API

Submit, scrub, edit, track, and manage professional, institutional, and dental claims (X12 837P/I/D) through the clearinghouse.

- **Human URL:** [https://www.waystar.com/our-platform/claim-management/claim-manager/](https://www.waystar.com/our-platform/claim-management/claim-manager/)

### Waystar Claim Status API

Query and monitor claim status across payers (X12 276/277) — received, accepted, pending, denied, paid.

- **Human URL:** [https://www.waystar.com/our-platform/claim-management/claim-monitoring/](https://www.waystar.com/our-platform/claim-management/claim-monitoring/)

### Waystar Remittance & ERA API

Retrieve electronic remittance advice (835/ERA), payments, and adjustments for automated payment posting and reconciliation.

- **Human URL:** [https://www.waystar.com/our-platform/payment-management/remit-manager/](https://www.waystar.com/our-platform/payment-management/remit-manager/)

### Waystar Denial & Appeal Management API

Identify denials, expose denial/remark codes and EOB detail, and support appeal creation, packaging, and resubmission.

- **Human URL:** [https://www.waystar.com/our-platform/denial-prevention-recovery/denial-recovery/](https://www.waystar.com/our-platform/denial-prevention-recovery/denial-recovery/)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/waystar)
- [Website](https://www.waystar.com/)
- [Documentation](https://developer.waystar.com/)
- [Sign Up / Partners](https://www.waystar.com/clients-partners/)
- [Login](https://www.waystar.com/login/)
- [Plans](plans/waystar-plans-pricing.yml)
- [Rate Limits](rate-limits/waystar-rate-limits.yml)
- [Fin Ops](finops/waystar-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
