# Lanes & Planes

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
