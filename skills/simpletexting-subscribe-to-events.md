---
generated: '2026-08-13'
method: generated
name: Subscribe to delivery and incoming-message events
description: Register an HTTPS endpoint to receive incoming messages, delivery and non-delivery reports, and unsubscribes.
api: openapi/simpletexting-webhooks-api-openapi.yml
operations: [createWebhook, getWebhooks, updateWebhook, deleteWebhook]
source: >-
  operationIds and trigger enum verified in openapi/simpletexting-webhooks-api-openapi.yml;
  payload shapes in openapi/simpletexting-webhook-reports-api-openapi.yml.
---

# Subscribe to delivery and incoming-message events

Base URL `https://api-app2.simpletexting.com/v2`.

## Auth
- `Authorization: Bearer <token>`. See `authentication/simpletexting-authentication.yml`.

## Steps
1. **Create the subscription** — `createWebhook` (`POST /api/webhooks`) with the required `url` and `triggers[]`, plus optional `requestPerSecLimit` (integer, **maximum 25**), `accountPhone` and `contactPhone` filters. Responds `201`; `400` on a bad body.
2. **Choose triggers** — `INCOMING_MESSAGE`, `OUTGOING_MESSAGE`, `DELIVERY_REPORT`, `NON_DELIVERED_REPORT`, `UNSUBSCRIBE_REPORT`.
3. **Handle the callbacks** — SimpleTexting POSTs JSON to your URL. The payload shapes are published as operations whose `servers[]` is *your* domain:
   - `incomingMessageReport` (`POST /report/incoming`) — `WebhookMessageDto`: `messageId`, `text`, `subject`, `mediaItems[]`, `accountPhone`, `contactPhone`, `timestamp`, `category`, `referenceType`.
   - `deliveryMessageReport` (`POST /report/delivery`) — `WebhookDeliveryReportDto`: `messageId`, `category`, `referenceType`, `accountPhone`, `contactPhone`, `carrier`.
   - `unsubscribeMessageReport` (`POST /report/unsubscribe`) — `WebhookUnsubscribeReportDto`: `contactId`, `phone`.
   Return HTTP `200`.
4. **Manage** — `getWebhooks` (`GET /api/webhooks`) lists subscriptions, `updateWebhook` (`PUT /api/webhooks/{webhookId}`) edits one (`404` if the id is unknown), `deleteWebhook` (`DELETE /api/webhooks/{webhookId}`) removes it (`204`).

## Security warning
- **Callbacks are unsigned.** SimpleTexting publishes no signature header, shared secret or verification procedure, so your endpoint cannot prove a request came from SimpleTexting. Use an unguessable path, restrict by source where you can, and treat payload contents as untrusted input. See `asyncapi/simpletexting-webhooks.yml`.
- Retry and ordering semantics are undocumented; make your handler idempotent on `messageId`.

## Errors
- Non-RFC-9457 `application/problem+json` envelope on the management API. See `errors/simpletexting-problem-types.yml`.
