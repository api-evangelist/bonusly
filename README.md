# Bonusly (bonusly)

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

Bonusly is an employee recognition and rewards platform that lets coworkers give each other small, frequent, public bonuses tied to company values, which recipients redeem for gift cards, custom rewards, donations, and more. The Bonusly REST API (base `https://bonus.ly/api/v1`) exposes the same surface the product is built on - bonuses, users, the reward catalog, redemptions, awards, company settings, and analytics - authenticated with a Bearer personal access token.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/bonusly/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/bonusly/refs/heads/main/apis.yml)

## Access Model

API access is a paid feature. The free tier (capped at up to 8 users) is intended for evaluation; the REST API, HRIS integrations, and analytics come with the paid **Team** and **Organization** plans. Authentication uses a **personal access token (PAT)** passed as `Authorization: Bearer <token>`. Tokens are minted by a Global or Tech admin (from Company Settings > Integrations) or by a user from their profile's API tab, and carry fine-grained **read / write / administer** scopes per resource - calling an endpoint without the required scope returns `403 Forbidden`. Tokens can live up to 365 days. A newer public surface is also served under `https://bonus.ly/api/public`, and Bonusly ships an MCP server (announced 2026-05-22) that fronts the same REST API for AI agents.

Rate limits vary by operation; exceeding one returns `429 Too Many Requests` with a `Retry-After` header, and limits can be raised on request. No fixed numeric request ceiling is published.

## Tags

- Employee Recognition
- Rewards
- Employee Engagement
- HR
- Company Culture
- Bonuses

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Bonusly Bonuses API

Create, list, retrieve, update, and delete bonuses - the public peer-to-peer recognition posts that carry points, a reason, hashtags, and one or more receivers. Includes an Atom feed of recent bonuses.

- **Human URL:** [https://docs.bonus.ly/reference/list-bonuses](https://docs.bonus.ly/reference/list-bonuses)
- **Base URL:** `https://bonus.ly/api/v1`

#### Tags

- Bonuses
- Recognition
- Points

#### Properties

- [Documentation](https://docs.bonus.ly/)
- [API Reference](https://docs.bonus.ly/reference/list-bonuses)
- [OpenAPI](openapi/bonusly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bonusly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bonusly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bonusly Users API

Manage company members - create, list, retrieve, update, and deactivate users; fetch the authenticated user via `/me`; autocomplete users by name; and pull a user's bonuses, redemptions, and achievements.

- **Human URL:** [https://docs.bonus.ly/reference/list-users](https://docs.bonus.ly/reference/list-users)
- **Base URL:** `https://bonus.ly/api/v1`

#### Tags

- Users
- Members
- Provisioning

#### Properties

- [API Reference](https://docs.bonus.ly/reference/list-users)
- [OpenAPI](openapi/bonusly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bonusly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bonusly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bonusly Rewards API

Browse the redemption catalog - the gift cards, donations, and custom company rewards a user can spend earned points on, filterable by country and reward request.

- **Human URL:** [https://docs.bonus.ly/reference/list-rewards](https://docs.bonus.ly/reference/list-rewards)
- **Base URL:** `https://bonus.ly/api/v1`

#### Tags

- Rewards
- Gift Cards
- Catalog

#### Properties

- [API Reference](https://docs.bonus.ly/reference/list-rewards)
- [OpenAPI](openapi/bonusly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bonusly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bonusly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bonusly Redemptions API

List and retrieve redemptions where users convert earned points into rewards, create a user redemption, and manage the custom-reward redemption workflow - listing, approving, and fulfilling custom rewards.

- **Human URL:** [https://docs.bonus.ly/reference/list-redemptions](https://docs.bonus.ly/reference/list-redemptions)
- **Base URL:** `https://bonus.ly/api/v1`

#### Tags

- Redemptions
- Rewards
- Fulfillment

#### Properties

- [API Reference](https://docs.bonus.ly/reference/list-redemptions)
- [OpenAPI](openapi/bonusly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bonusly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bonusly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bonusly Analytics API

Queue and read analytics snapshots for recognition activity - request an asynchronous snapshot of analytics users or recognition events, poll its status, and list the resulting rows for engagement reporting.

- **Human URL:** [https://docs.bonus.ly/reference/analytics-healthcheck](https://docs.bonus.ly/reference/analytics-healthcheck)
- **Base URL:** `https://bonus.ly/api/v1`

#### Tags

- Analytics
- Snapshots
- Reporting

#### Properties

- [API Reference](https://docs.bonus.ly/reference/analytics-healthcheck)
- [OpenAPI](openapi/bonusly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bonusly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bonusly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bonusly Company API

Retrieve and update company-level settings and read company achievements - the account configuration that governs allowances, values, and recognition behavior across the organization.

- **Human URL:** [https://docs.bonus.ly/reference/retrieve-company](https://docs.bonus.ly/reference/retrieve-company)
- **Base URL:** `https://bonus.ly/api/v1`

#### Tags

- Company
- Settings
- Administration

#### Properties

- [API Reference](https://docs.bonus.ly/reference/retrieve-company)
- [OpenAPI](openapi/bonusly-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bonusly.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bonusly.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/bonusly)
- [LinkedIn](https://www.linkedin.com/company/bonusly)
- [Website](https://bonusly.com)
- [Documentation](https://docs.bonus.ly/)
- [Plans](plans/bonusly-plans-pricing.yml)
- [Rate Limits](rate-limits/bonusly-rate-limits.yml)
- [Fin Ops](finops/bonusly-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
