# Bonusly (bonusly)

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
