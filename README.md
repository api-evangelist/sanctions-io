# sanctions.io (sanctions-io)

sanctions.io is a sanctions, PEP, and criminal watchlist screening API for AML (anti-money laundering) compliance. The REST API (base `https://api.sanctions.io`) screens individuals, entities, vessels, and aircraft against 75+ sanctions lists from 30+ jurisdictions (OFAC SDN and Non-SDN, EU, UN, HM Treasury, and more), over one million politically exposed person (PEP) records, criminal watchlists like Interpol Red Notices and FBI Most Wanted, and adverse media from 60,000+ news sources. It supports real-time single screening, batch screening of up to 10,000 records per request, continuous monitoring with webhook alerts, and a full sanctions database export.

Access is genuinely self-serve: a 7-day free trial (no credit card) at [api.sanctions.io/users/signup](https://api.sanctions.io/users/signup) issues a working API key with access to all API features, and the docs publish a shared test token that returns real but partial data for integration testing. Authentication is a Bearer API token in the Authorization header, with the API version selected via the Accept header (e.g. `application/json; version=2.3`; the adverse media endpoint requires `version=3.0`). The current API reference at [api-docs.sanctions.io](https://api-docs.sanctions.io/) covers the Screening API v2.3 and Monitoring API v3.1. Beyond the trial, pricing is volume-based - published packages have included 5,000 screenings for $899, 50,000 for $2,999, and 200,000 for $5,999 (renewing after twelve months or once consumed), with custom Enterprise plans from 25,000+ monthly screenings quoted through a pricing calculator. The database exporter endpoint is gated to specific plans.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sanctions-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sanctions-io/refs/heads/main/apis.yml)

## Tags

- Anti-Money Laundering
- AML
- Sanctions Screening
- Compliance
- PEP Screening
- Watchlists
- KYC
- RegTech

## Timestamps

- **Created:** 2026-07-11
- **Modified:** 2026-07-11

## APIs

### sanctions.io Screening API

Real-time single screening via the search endpoint - query a name (individual, entity, vessel, or aircraft) against selected sanctions, PEP, and criminal watchlist sources and get back scored matches. Tune results with `min_score` confidence (0.8-1.0), `data_source` short codes, `entity_type`, `country`, `date_of_birth`, `identifier`, and name-match boosting. Average response time is around 500-600ms for transaction and onboarding use cases.

- **Human URL:** [https://api-docs.sanctions.io/](https://api-docs.sanctions.io/)
- **Base URL:** `https://api.sanctions.io`

#### Tags

- Sanctions Screening
- AML
- PEP Screening

#### Properties

- [Documentation](https://api-docs.sanctions.io/)
- [Product Page](https://www.sanctions.io/solutions/screening-api)
- [OpenAPI](openapi/sanctions-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sanctions-io.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sanctions-io.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### sanctions.io Batch Screening API

Screen up to 10,000 names in a single API request for large-scale compliance checks such as periodic customer base audits, bulk vendor onboarding, or regulatory reporting. Create, list, retrieve, and delete batch screenings and fetch batch results; webhook events notify your systems when batch results are ready.

- **Human URL:** [https://api-docs.sanctions.io/](https://api-docs.sanctions.io/)
- **Base URL:** `https://api.sanctions.io`

#### Tags

- Batch Screening
- AML
- Compliance

#### Properties

- [Documentation](https://api-docs.sanctions.io/)
- [OpenAPI](openapi/sanctions-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sanctions-io.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sanctions-io.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### sanctions.io Adverse Media API

Search news articles related to specific individuals, entities, or subjects using custom keywords, drawing on 60,000+ global news sources for due diligence and AML compliance. Requires the version 3.0 Accept header; adverse media can also be included in batch screening and monitoring by passing the `ADV-MEDIA` data source short code.

- **Human URL:** [https://api-docs.sanctions.io/](https://api-docs.sanctions.io/)
- **Base URL:** `https://api.sanctions.io`

#### Tags

- Adverse Media
- Due Diligence
- AML

#### Properties

- [Documentation](https://api-docs.sanctions.io/)
- [Product Page](https://www.sanctions.io/data/adverse-media-screening)
- [OpenAPI](openapi/sanctions-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sanctions-io.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sanctions-io.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### sanctions.io Data Sources API

List all sanctions and watchlist sources available for screening - each with the `short_name` code used in the `data_source` screening parameter (OFAC SDN, EU CFSP, UK HM Treasury, FBI, FATF, Interpol, and dozens more). A separate exporter endpoint returns a full CSV export of the sanctions and crime database for plans that include it.

- **Human URL:** [https://api-docs.sanctions.io/](https://api-docs.sanctions.io/)
- **Base URL:** `https://api.sanctions.io`

#### Tags

- Watchlists
- Data Sources
- Sanctions Lists

#### Properties

- [Documentation](https://api-docs.sanctions.io/)
- [OpenAPI](openapi/sanctions-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sanctions-io.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sanctions-io.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### sanctions.io Monitoring API

Continuously monitor customers, vendors, and counterparties against watchlists - create and manage monitoring entries, list and filter them by alerts and review status, and review or resolve monitoring results (for example marking a match Real Positive). New matches or record updates raise alerts that can be delivered to your systems by webhook.

- **Human URL:** [https://api-docs.sanctions.io/](https://api-docs.sanctions.io/)
- **Base URL:** `https://api.sanctions.io`

#### Tags

- Continuous Monitoring
- Alerts
- AML

#### Properties

- [Documentation](https://api-docs.sanctions.io/)
- [OpenAPI](openapi/sanctions-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sanctions-io.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sanctions-io.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### sanctions.io Account Management API

Manage the account around your screening integration - create, list, and delete API tokens, read and update company details and the company config (including registering webhook endpoints secured with SHA-256 signatures), invite and manage users, view plan subscriptions, and count screenings performed.

- **Human URL:** [https://api-docs.sanctions.io/](https://api-docs.sanctions.io/)
- **Base URL:** `https://api.sanctions.io`

#### Tags

- Account Management
- API Tokens
- Webhooks

#### Properties

- [Documentation](https://api-docs.sanctions.io/)
- [OpenAPI](openapi/sanctions-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sanctions-io.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sanctions-io.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/sanctions-io-llc)
- [Website](https://www.sanctions.io)
- [Documentation](https://api-docs.sanctions.io/)
- [Pricing](https://www.sanctions.io/pricing-calculator)
- [Signup](https://api.sanctions.io/users/signup)
- [Blog](https://www.sanctions.io/blog)
- [Support](https://help.sanctions.io/)
- [Plans](plans/sanctions-io-plans-pricing.yml)
- [Rate Limits](rate-limits/sanctions-io-rate-limits.yml)
- [Fin Ops](finops/sanctions-io-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
