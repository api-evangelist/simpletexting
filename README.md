# SimpleTexting (simpletexting)

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

SimpleTexting is a business SMS and MMS marketing platform. Its v2 REST API lets developers send single text messages, run bulk campaigns to lists and segments, manage contacts and contact lists, upload MMS media, provision sending numbers, and subscribe to delivery and incoming-message webhooks, all authenticated with a bearer token.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/simpletexting/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/simpletexting/refs/heads/main/apis.yml)

## Tags

- SMS
- MMS
- Messaging
- Marketing
- Text Messaging

## Timestamps

- **Created:** 2026-06-20
- **Modified:** 2026-06-20

## APIs

### SimpleTexting Messages API

Send a single SMS or MMS message to one contact, evaluate a message body for credit cost and segment count before sending, and retrieve sent and received messages with pagination.

- **Human URL:** [https://api-doc.simpletexting.com/](https://api-doc.simpletexting.com/)
- **Base URL:** `https://api-app2.simpletexting.com/v2`

#### Tags

- Messages
- SMS
- MMS

#### Properties

- [Documentation](https://simpletexting.com/api/docs/)
- [API Reference](https://api-doc.simpletexting.com/)
- [OpenAPI](openapi/simpletexting-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/simpletexting.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/simpletexting.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SimpleTexting Contacts API

Create, read, update, upsert, and delete individual contacts with first/last name, email, birthday, custom fields, and list membership, plus asynchronous batch update and batch delete operations and access to custom fields and dynamic segments.

- **Human URL:** [https://api-doc.simpletexting.com/](https://api-doc.simpletexting.com/)
- **Base URL:** `https://api-app2.simpletexting.com/v2`

#### Tags

- Contacts
- CRM

#### Properties

- [Documentation](https://simpletexting.com/api/docs/)
- [API Reference](https://api-doc.simpletexting.com/)
- [OpenAPI](openapi/simpletexting-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/simpletexting.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/simpletexting.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SimpleTexting Lists API

Create, read, rename, and delete contact lists, and add or remove contacts from a list by phone number or contact id.

- **Human URL:** [https://api-doc.simpletexting.com/](https://api-doc.simpletexting.com/)
- **Base URL:** `https://api-app2.simpletexting.com/v2`

#### Tags

- Lists
- Segments

#### Properties

- [Documentation](https://simpletexting.com/api/docs/)
- [API Reference](https://api-doc.simpletexting.com/)
- [OpenAPI](openapi/simpletexting-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/simpletexting.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/simpletexting.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SimpleTexting Campaigns API

Send a bulk campaign immediately to one or more lists or segments using a message template, and retrieve campaigns with pagination.

- **Human URL:** [https://api-doc.simpletexting.com/](https://api-doc.simpletexting.com/)
- **Base URL:** `https://api-app2.simpletexting.com/v2`

#### Tags

- Campaigns
- Bulk Messaging

#### Properties

- [Documentation](https://simpletexting.com/api/docs/)
- [API Reference](https://api-doc.simpletexting.com/)
- [OpenAPI](openapi/simpletexting-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/simpletexting.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/simpletexting.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SimpleTexting Autoresponders API

Keyword and autoresponder workflows, including renting and configuring keywords and exporting autoresponder analytics, exposed through the SimpleTexting v1 API surface that complements the v2 REST API.

- **Human URL:** [https://simpletexting.com/api/docs/](https://simpletexting.com/api/docs/)
- **Base URL:** `https://app2.simpletexting.com/v1`

#### Tags

- Autoresponders
- Drip
- Keywords

#### Properties

- [Documentation](https://simpletexting.com/api/docs/)
- [OpenAPI](openapi/simpletexting-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### SimpleTexting Sending Numbers API

Retrieve the sending phone numbers provisioned on the account and general tenant information, including the account credit balance.

- **Human URL:** [https://api-doc.simpletexting.com/](https://api-doc.simpletexting.com/)
- **Base URL:** `https://api-app2.simpletexting.com/v2`

#### Tags

- Sending Numbers
- Phones

#### Properties

- [Documentation](https://simpletexting.com/api/docs/)
- [API Reference](https://api-doc.simpletexting.com/)
- [OpenAPI](openapi/simpletexting-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/simpletexting.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/simpletexting.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### SimpleTexting Webhooks API

Create, read, update, and delete webhooks that fire on incoming and outgoing messages, delivery and non-delivery reports, and unsubscribe events, with an optional per-second request rate limit.

- **Human URL:** [https://api-doc.simpletexting.com/](https://api-doc.simpletexting.com/)
- **Base URL:** `https://api-app2.simpletexting.com/v2`

#### Tags

- Webhooks
- Events

#### Properties

- [Documentation](https://simpletexting.com/api/docs/)
- [API Reference](https://api-doc.simpletexting.com/)
- [OpenAPI](openapi/simpletexting-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Review](review.yml)
- [Postman Collection](collections/simpletexting.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/simpletexting.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/simpletexting)
- [Website](https://simpletexting.com/)
- [Documentation](https://simpletexting.com/api/docs/)
- [Plans](plans/simpletexting-plans-pricing.yml)
- [Rate Limits](rate-limits/simpletexting-rate-limits.yml)
- [Fin Ops](finops/simpletexting-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
