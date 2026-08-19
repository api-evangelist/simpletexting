---
generated: '2026-08-13'
method: generated
name: Build and maintain a contact list
description: Create a list, add contacts to it one at a time or in bulk, and keep it current with batch updates.
api: openapi/simpletexting-contact-lists-api-openapi.yml
operations: [createList, createContact, addContactToList, getContacts, processBatchUpdate, getBatchUpdateResults]
source: >-
  operationIds verified in openapi/simpletexting-contact-lists-api-openapi.yml,
  openapi/simpletexting-contacts-api-openapi.yml and
  openapi/simpletexting-contacts-batch-operations-api-openapi.yml.
---

# Build and maintain a contact list

Base URL `https://api-app2.simpletexting.com/v2`.

## Auth
- `Authorization: Bearer <token>`. See `authentication/simpletexting-authentication.yml`.

## Steps
1. **Create the list** — `createList` (`POST /api/contact-lists`) with `name`. Responds `201`. Lists can afterwards be addressed by id **or** by name in the path (`{listIdOrName}`).
2. **Create contacts** — `createContact` (`POST /api/contacts`) with `contactPhone` plus optional `firstName`, `lastName`, `email`, `birthday`, `comment`, `lists[]` and `customFields`. Passing `lists[]` at creation time is the one-step path; otherwise use step 3.
3. **Attach an existing contact** — `addContactToList` (`POST /api/contact-lists/{listIdOrName}/contacts`). Detach with `removeContactFromGroup` (`DELETE /api/contact-lists/{listIdOrName}/contacts/{contactPhoneOrId}`).
4. **Bulk changes** — `processBatchUpdate` (`POST /api/contacts-batch/batch-update`) takes `updates[]` and an optional `listsReplacement` flag (replace list membership rather than append). It is **asynchronous**: it responds `201` with a task id, and you poll `getBatchUpdateResults` (`GET /api/contacts-batch/batch-update/{taskId}`) for per-contact results. Bulk removal is `processBatchDelete` (`POST /api/contacts-batch/batch-delete`) with `contactPhones[]`.
5. **Verify** — `getContacts` (`GET /api/contacts`) with `page` (zero-based), `size` (max 500), `since` (ISO 8601) and `direction` (`ASC`/`DESC`). Read `totalElements` to confirm the count.

## Consent
- `Contact.subscriptionStatus` records opt-in state, and an `UNSUBSCRIBE_REPORT` webhook fires when someone texts STOP. Never re-add a contact that unsubscribed — see `conformance/simpletexting-conformance.yml` for SimpleTexting's published TCPA/CTIA/10DLC posture.

## Errors
- Non-RFC-9457 `application/problem+json` envelope. See `errors/simpletexting-problem-types.yml`.
