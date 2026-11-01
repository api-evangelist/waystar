# Waystar

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

Waystar is a healthcare payments and revenue cycle management (RCM) software company that operates a national clearinghouse connecting providers to payers. Its cloud platform spans financial clearance (eligibility, prior authorization, patient estimation), claim management, payment and remittance management, and denial prevention and recovery. Waystar exposes integration through REST APIs, web services, HL7, sFTP/batch, RPA, and X12 EDI transactions (270/271 eligibility, 276/277 claim status, 837 claims, 835 remittance/ERA, 278 authorization). API access is delivered through a partner/developer program at developer.waystar.com; the portal renders its full documentation navigation to anyone but serves a login form in place of every document body, and sandbox accounts are provisioned by email rather than self-service. Waystar publishes no OpenAPI, no llms.txt, no MCP server, no agent card and no client SDK in any package registry. Authentication is six hand-rolled schemes rather than one - HMAC-SHA1 body signatures on the classic Developer Suite, HMAC-SHA256 Authorization headers on Patient Estimation, credentials in the POST body on the eligibility gateway, HTTP Basic, WS-Security UsernameToken inside CAQH CORE SOAP envelopes, and X.509 client certificates - with no OAuth 2.0 and no OpenID Connect anywhere. The API surface below is documented from Waystar's public product pages, its developer-portal structure and the underlying X12 standards rather than from a published machine-readable definition.

**Areas:** Healthcare · Revenue Cycle Management · Clearinghouse · Healthcare Payments · Medical Billing · X12 EDI · Eligibility · Claims · Health Insurance

## Waystar on APIs.io

Everything profiled for Waystar is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/waystar/](https://apis.io/providers/waystar/)** — or go straight to one of the APIs or properties below.

### APIs (7)

- [Waystar Eligibility Verification API](https://apis.io/apis/waystar/waystar-eligibility-verification-api/) — Real-time and batch insurance eligibility and benefits verification, exchanging X12 270 inquiries and 271 responses to confirm coverage, plan details,…
- [Waystar Authorization & Referral API](https://apis.io/apis/waystar/waystar-prior-authorization-api/) — Automates prior authorization and referral determination and status, modeled on the X12 278 health care services review request/response. Covers submitting…
- [Waystar Patient Estimation API](https://apis.io/apis/waystar/waystar-patient-estimation-api/) — Produces pre-service, good-faith patient cost estimates by combining eligibility/benefit data, contracted rates, and procedure codes to support price…
- [Waystar Claim Management API](https://apis.io/apis/waystar/waystar-claim-management-api/) — Submits, scrubs, edits, tracks, and manages professional, institutional, and dental claims through Waystar's clearinghouse, modeled on the X12…
- [Waystar Claim Status API](https://apis.io/apis/waystar/waystar-claim-status-api/) — Queries and monitors claim status across payers, modeled on the X12 276 status inquiry and 277 status response - returning received, accepted, pending,…
- [Waystar Remittance & ERA API](https://apis.io/apis/waystar/waystar-remittance-era-api/) — Retrieves electronic remittance advice (835/ERA), payments, and adjustments for automated payment posting and reconciliation, with raw X12 835 artifacts and…
- [Waystar Denial & Appeal Management API](https://apis.io/apis/waystar/waystar-denial-management-api/) — Identifies denied claims, exposes denial and remark codes and explanation-of-benefits detail, and supports appeal creation, packaging, and resubmission…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Waystar Authentication](https://apis.io/security/waystar/waystar-authentication/)
- [Waystar Domain Security](https://apis.io/security/waystar/waystar-domain-security/)
- [Waystar Vulnerability Disclosure](https://apis.io/security/waystar/waystar-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Waystar Plans Pricing](https://apis.io/plans/waystar/waystar-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Waystar Rate Limits](https://apis.io/rate-limits/waystar/waystar-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Waystar Finops](https://apis.io/finops/waystar/waystar-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.waystar.com/)
- [Documentation](https://developer.waystar.com/)
- [Getting started](https://developer.waystar.com/documents/integration-basics/)
- [API reference](https://developer.waystar.com/documents/)
- [Pricing](https://www.waystar.com/clients-partners/)
- [Sign up](https://www.waystar.com/clients-partners/)
- [Support](https://www.waystar.com/support/)
- [Blog](https://www.waystar.com/blog/)
- [Security](https://www.waystar.com/responsible-disclosure/)
- [Terms of service](https://www.waystar.com/terms/)
- [Privacy policy](https://www.waystar.com/privacy-policy/)
- [GitHub](https://github.com/WaystarInc)
- [Status](http://status.esolutionsinc.com/)

## API Evangelist rating

**Kin Score 43.9** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 62.5 |
| Contract quality | 0.0 |
| Contract governance | 18.2 |
| Operational transparency | 60.5 |
| Developer ergonomics | 64.3 |
| Access clarity | 65.8 |

**Agent readiness 11.2** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | — |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | documented (partial credit) |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 27.2** — Insurance

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/waystar/](https://apis.io/providers/waystar/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Waystar: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/waystar/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
