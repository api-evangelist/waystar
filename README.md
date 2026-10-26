# Waystar (waystar)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Waystar is a healthcare payments and revenue cycle management (RCM) software company that operates a national clearinghouse connecting providers to payers. Its cloud platform spans financial clearance (eligibility, prior authorization, patient estimation), claim management, payment and remittance management, and denial prevention and recovery. Waystar integrates with practice management (PM), hospital information systems (HIS), and EHRs through REST APIs, web services, HL7, sFTP/batch, RPA (bots), and X12 EDI transactions.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/waystar/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/waystar/refs/heads/main/apis.yml)

## Access Model — Partner / Developer Gated

Waystar operates a developer portal at [developer.waystar.com](https://developer.waystar.com/), and its public material describes integration via "REST APIs, web services, sFTP, HL7, batch, X12 EDI, RPA (bot)" along with "HMAC Security for Web Services / API Information" and a "Credential Management API." However:

- **No public OpenAPI definition is published.** `/openapi.json`, `/openapi.yaml`, `/swagger.json`, `/api-docs` and `/llms.txt` return 404 on `developer.waystar.com`, `www.waystar.com` and on every documented Waystar/ZirMed API host. There is no MCP server, no A2A agent card, no `/.well-known/` document, and no client SDK in npm, PyPI, RubyGems, NuGet, crates.io, Packagist or Maven Central.
- **The developer portal renders its full documentation navigation publicly but serves a login form in place of every document body.** Specifications exist as PDF companion guides behind that login.
- **Authentication is six hand-rolled schemes, not one** — HMAC-SHA1 body signature, HMAC-SHA256 `Authorization` header, credentials in the POST body, HTTP Basic, WS-Security UsernameToken inside CAQH CORE SOAP, and X.509 client certificates — with **no OAuth 2.0 and no OpenID Connect**. See [`authentication/`](authentication/waystar-authentication.yml).
- **Base URLs are now recorded** for six of the seven APIs. They are Waystar's documented product hosts; several sit on `zirmed.com`, Waystar's own legacy brand (both `zirmed.com` and `www.zirmed.com` 301 to `waystar.com`). Every host was verified to resolve inside Waystar's contiguous `69.2.x.x` netblock. The Denial & Appeal Management API has none because Waystar documents none.
- Access is obtained by becoming a Waystar client or technology partner via [waystar.com/clients-partners](https://www.waystar.com/clients-partners/). Sandbox accounts are provisioned by email, not self-service.

This is an **honest gated profile**: the provider is real and exposes substantial programmatic integration, but the concrete contract is not published in machine-readable form.

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

**Waystar pages**

- [Website](https://www.waystar.com/) · [LinkedIn](https://www.linkedin.com/company/waystar) · [Blog](https://www.waystar.com/blog/)
- [Developer portal](https://developer.waystar.com/) · [API reference index](https://developer.waystar.com/documents/) · [Integration basics](https://developer.waystar.com/documents/integration-basics/)
- [Clients & partners (sign up)](https://www.waystar.com/clients-partners/) · [Login](https://www.waystar.com/login/) · [Support](https://www.waystar.com/support/)
- [Terms and conditions](https://www.waystar.com/terms/) · [Privacy policy](https://www.waystar.com/privacy-policy/) · [Responsible disclosure](https://www.waystar.com/responsible-disclosure/)
- [GitHub organization](https://github.com/WaystarInc) — two forked CI/CD example repos, last pushed 2023, no API artifacts
- [Status page](http://status.esolutionsinc.com/) — a first-party Pingdom uptime dashboard on the Waystar-owned `esolutionsinc.com` domain. **HTTP only**, unlinked from every Waystar property, and it does not monitor the newer API hosts.

**Artifacts in this repository**

- [Authentication](authentication/waystar-authentication.yml) · [Conventions / idempotency](conventions/waystar-conventions.yml) · [Error catalog](errors/waystar-problem-types.yml)
- [Lifecycle](lifecycle/waystar-lifecycle.yml) · [Conformance](conformance/waystar-conformance.yml) · [Sandbox](sandbox/waystar-sandbox.yml) · [Data model](data-model/waystar-data-model.yml)
- [Packages](packages/waystar-packages.yml) · [MCP](mcp/waystar-mcp.yml) · [llms.txt](llms/waystar-llms.txt) · [Well-known probe](well-known/waystar-well-known.yml)
- [Plans](plans/waystar-plans-pricing.yml) · [Rate limits](rate-limits/waystar-rate-limits.yml) · [Fin Ops](finops/waystar-finops.yml)
- [Domain security](security/waystar-domain-security.yml) · [Vulnerability disclosure](security/waystar-vulnerability-disclosure.yml)

**Deliberately absent** — no `Compliance`, `TrustCenter`, `WellKnown`, `SecurityTxt`, `MCPServer`, `AgentCard`, `AgentSkill`, `SDKs`, `Deprecation`, `Pricing`, `Roadmap` or `Postman` pointer is emitted, because Waystar publishes none of them. The certifications Waystar claims (HIPAA, PCI DSS, SSAE 16, EHNAC, GLBA) sit behind the developer-portal login, so they are recorded in `conformance/` but not asserted as published.

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
