---
generated: '2026-08-13'
method: generated
name: Send an MMS with uploaded media
description: Upload an image (or ingest one from a URL), then attach it to an MMS send.
api: openapi/simpletexting-media-items-api-openapi.yml
operations: [upload, uploadByLink, getMediaItems, evaluateMessage, createMessage]
source: >-
  operationIds verified in openapi/simpletexting-media-items-api-openapi.yml and
  openapi/simpletexting-messages-api-openapi.yml.
---

# Send an MMS with uploaded media

Base URL `https://api-app2.simpletexting.com/v2`.

## Auth
- `Authorization: Bearer <token>`. See `authentication/simpletexting-authentication.yml`.

## Steps
1. **Get the media into the account** — either
   - `upload` (`POST /api/mediaitems/upload`) with a `multipart/form-data` file, or
   - `uploadByLink` (`POST /api/mediaitems/loadByLink`) to have SimpleTexting fetch it from a URL you supply.
   Both return an `StFileDto`: `id`, `name`, `size`, `contentType`, `ext`, `gallery`, `status`, `link`, `canDelete`.
2. **Confirm it is stored** — `getMediaItems` (`GET /api/mediaitems`, paginated) or `getMediaItem` (`GET /api/mediaitems/{mediaItemId}`). Keep the `id` — that is what the message references.
3. **Price the MMS** — `evaluateMessage` (`POST /api/messages/evaluate`) with `mode: MMS_PREFERRED`, your `text`, optional `subject` and `mediaItems: [<id>]`. An MMS costs 3 credits; check `sumOfCredits` and `warnings[]`.
4. **Send** — `createMessage` (`POST /api/messages`) with `contactPhone`, `mode: MMS_PREFERRED`, `text`, `mediaItems: [<id>]`, optional `subject` (MMS only) and `fallbackText` (used when the recipient's carrier cannot take MMS).
5. **Clean up** — `delete` (`DELETE /api/mediaitems/{mediaItemId}`) removes a media item (`204`), but only when `canDelete` is true.

## Notes
- `subject` is meaningful only for MMS. Always set `fallbackText` when using `MMS_PREFERRED`, or SMS recipients get the raw text with no context.
- Use `SINGLE_SMS_STRICTLY` when you need a hard guarantee of one plain SMS instead.

## Errors
- Non-RFC-9457 `application/problem+json` envelope. See `errors/simpletexting-problem-types.yml`.
