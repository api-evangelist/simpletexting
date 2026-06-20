# SimpleTexting (simpletexting)

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
