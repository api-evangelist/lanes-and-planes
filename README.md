# Lanes & Planes

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Lanes & Planes is a Munich-based travel and expense (T&E) management platform that positions itself as the financial infrastructure for European corporate travel. It covers the full T&E lifecycle in one system — travel request, digital approval flows, booking, and final accounting — across European rail (Deutsche Bahn, ÖBB, SBB, SNCF), flights including NDC content, 7M+ hotels, Airbnb for Work, rental cars, and ground mobility including the Deutschland-Ticket.

The product is built for finance departments: VAT-compliant automated invoicing, German per-diem (VMA) tax logic, centralized billing on a single creditor, real-time budget tracking, and automated travel-policy enforcement. It integrates with DATEV, SAP, Microsoft Dynamics, Sage and Addison on the ERP side, and with HRIS platforms via a native Personio connector plus an External API (ExtAPI) for Workday, BambooHR and HiBob.

Backed by: battery-ventures

## API posture

Lanes & Planes has **no public API program**. There is no developer portal, API reference, OpenAPI definition, SDK, CLI, sandbox, changelog, or self-service credential flow. The External API (ExtAPI) is real — the company names it in its own `llms.txt` — but it is partner- and customer-gated, arranged through the implementation manager assigned at onboarding. `api.lanes-planes.com` is a live host but serves no documentation or discovery document.

This repo therefore captures identity, security posture, and compliance rather than API artifacts. Nothing about the API surface has been inferred or invented.

## Artifacts

| Artifact | Method | Notes |
|---|---|---|
| `llms/lanes-and-planes-llms.txt` | searched | First-party `/llms.txt`, saved verbatim — an unusually rich one, authored explicitly for AI models |
| `well-known/lanes-and-planes-well-known.yml` | probed | Negative result: no `/.well-known/` documents on any host |
| `security/lanes-and-planes-domain-security.yml` | probed | TLS 1.3, HSTS on www, CAA present, SPF + DMARC (`p=none`), no DNSSEC |
| `security/lanes-and-planes-trust-center.yml` | searched | Vanta-hosted trust center; ISO 27001 + ISO 9001 |
| `authentication/lanes-and-planes-authentication.yml` | searched | SAML 2.0 SSO; ExtAPI auth model undisclosed |
| `conformance/lanes-and-planes-conformance.yml` | searched | SAML 2.0, ISO 27001/9001, GDPR, IATA NDC, EU VAT invoicing |
