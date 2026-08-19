---
generated: '2026-08-13'
method: generated
name: Run a bulk campaign to a list or segment
description: Compose a message template and send it immediately to one or more contact lists and/or dynamic segments, then read the outcome.
api: openapi/simpletexting-campaigns-api-openapi.yml
operations: [getLists, getSegments, evaluateMessage, createCampaign, getCampaign]
source: >-
  operationIds verified in openapi/simpletexting-campaigns-api-openapi.yml,
  openapi/simpletexting-contact-lists-api-openapi.yml,
  openapi/simpletexting-contact-segments-api-openapi.yml and
  openapi/simpletexting-messages-api-openapi.yml.
---

# Run a bulk campaign to a list or segment

Base URL `https://api-app2.simpletexting.com/v2`.

## Auth
- `Authorization: Bearer <token>`. See `authentication/simpletexting-authentication.yml`.

## Steps
1. **Choose the audience** — `getLists` (`GET /api/contact-lists`) for manually-managed lists and `getSegments` (`GET /api/contact-segments`) for rule-based segments. Both paginate with `page`/`size` and return `{content, totalPages, totalElements}`. Collect the ids you want as `listIds[]` and `segmentIds[]`.
2. **Price the body** — `evaluateMessage` (`POST /api/messages/evaluate`) with the same `mode` and `text` you intend to use. Multiply `sumOfCredits` by the audience size before sending: a campaign spends credits per recipient.
3. **Create the campaign** — `createCampaign` (`POST /api/campaigns`) with the required `title` and `messageTemplate` (itself requiring `mode` and `text`; optional `subject`, `fallbackText`, `mediaItems[]`), plus `listIds[]` and/or `segmentIds[]`, optional `accountPhone` and `customFieldsMaxLength`. Responds `201`.
4. **Read the outcome** — `getCampaign` (`GET /api/campaigns/{campaignId}`) returns the campaign with its outcome counters and any tracking links. `getCampaigns` (`GET /api/campaigns`) pages the history.

## Merge tags
- Personalize `messageTemplate.text` with the account's custom-field merge tags — list them with `getCustomFields` (`GET /api/custom-fields`), which returns `label`, `type`, `mergeTag` and `defaultMaxLength`. `customFieldsMaxLength` on the campaign caps substituted length so the message does not silently spill into a higher credit tier.

## Cautions
- No idempotency key exists. A retried `createCampaign` sends the campaign twice, to the whole audience. See `conventions/simpletexting-conventions.yml`.
- Throughput is governed by number type and carrier registration (10DLC, toll-free, short code), not by a documented API quota. See `rate-limits/simpletexting-rate-limits.yml`.

## Errors
- Non-RFC-9457 `application/problem+json` envelope. See `errors/simpletexting-problem-types.yml`.
