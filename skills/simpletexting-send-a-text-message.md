---
generated: '2026-08-13'
method: generated
name: Send a single SMS or MMS
description: Send one text message to one contact phone number, after checking what it will cost in credits.
api: openapi/simpletexting-messages-api-openapi.yml
operations: [getTenantPhones, evaluateMessage, createMessage, getMessage]
source: >-
  operationIds verified in openapi/simpletexting-messages-api-openapi.yml and
  openapi/simpletexting-tenant-phones-api-openapi.yml.
---

# Send a single SMS or MMS

Base URL `https://api-app2.simpletexting.com/v2`.

## Auth
- `Authorization: Bearer <token>` on every request. See `authentication/simpletexting-authentication.yml`.
- Access is approval-gated: SimpleTexting must approve the account for API use before a token works.

## Idempotency
- **There is none.** No `Idempotency-Key` exists. A blind retry of `createMessage` sends and bills a second message. Deduplicate client-side and correlate on the returned message id. See `conventions/simpletexting-conventions.yml`.

## Steps
1. **Pick the sending number** — `getTenantPhones` (`GET /api/phones`) returns the numbers provisioned on the account. Use one as `accountPhone`; omit it to use the primary number.
2. **Price the message first** — `evaluateMessage` (`POST /api/messages/evaluate`) with `mode` and `text`. The `MessageInfo` response gives `detectedCategory` (SMS / EXTENDED_SMS / MMS), `length`, `remains`, `maxLength`, `unicode`, `sumOfCredits`, plus `warnings[]` and `errors[]`. This is the only way to learn the credit cost before spending it.
3. **Send it** — `createMessage` (`POST /api/messages`) with the required `contactPhone`, `mode` and `text`. Optional: `accountPhone`, `subject` (MMS only), `fallbackText`, `mediaItems[]`.
   - `mode`: `AUTO` (default, SimpleTexting picks the type), `SINGLE_SMS_STRICTLY` (send one SMS or fail), `MMS_PREFERRED` (MMS, falling back to SMS where the carrier does not support it).
   - Responds `201` with the created message.
4. **Confirm** — `getMessage` (`GET /api/messages/{messageId}`) to read the stored message back, and subscribe to `DELIVERY_REPORT` for carrier confirmation (see `simpletexting-subscribe-to-events.md`).

## Credits
- SMS ≤160 chars = 1 credit, EXTENDED_SMS (≤306) = 2, MMS = 3. `evaluateMessage.sumOfCredits` is authoritative for a given body.

## Errors
- `401` `ERR_AUTH_TOKEN_MISSING` — no bearer token. Errors arrive as `application/problem+json` but are **not** RFC 9457; the shape is `{status, errorCode, code, message, errorDetails, path, timestamp}`. See `errors/simpletexting-problem-types.yml`.
- The spec declares no `429` and no `5xx` anywhere. Treat any non-2xx as retryable only after inspecting `errorCode`, and never blind-retry a send.
