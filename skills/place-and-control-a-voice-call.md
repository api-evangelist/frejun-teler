---
name: place-and-control-a-voice-call
description: Place an outbound programmable voice call with Teler and control it live (play audio, send DTMF, transfer, hang up).
api: Teler Voice API
operations:
  - initiate_call
  - retrieve_voice_call
  - play_audio
  - send_dtmf
  - transfer_call
  - hangup_call
  - list_webhook_events
---

# Place and control a voice call

All requests go to `https://api.frejun.ai` and carry your secret key in the
`x-api-key` header. A missing or invalid key returns `403`.

## Steps

1. **Initiate the call** — `POST /api/v1/voice/calls/initiate` (`initiate_call`).
   Provide the `from_number` (must be a provisioned virtual number), the
   `to_number`, and the voice-app / flow that drives the call. The response
   returns the call session id (`cs_` prefix). Do not use the deprecated
   `POST /api/v1/calls/initiate` (`initiate_call_legacy`).
2. **Track state** — `GET /api/v1/voice/calls/{call_id}` (`retrieve_voice_call`)
   returns the current `CallSessionState`. Call-control operations only succeed
   while the call is live; otherwise they return `409 call_not_live`.
3. **Control the live call** as needed:
   - `POST /api/v1/voice/calls/{call_id}/play` (`play_audio`) to play audio.
   - `POST /api/v1/voice/calls/{call_id}/dtmf` (`send_dtmf`) to send DTMF digits.
   - `POST /api/v1/voice/calls/{call_id}/transfer` (`transfer_call`) — returns
     `202 Accepted`; a second transfer while one is in flight returns
     `409 transfer_in_progress` (`type: invalid_state`).
   - `POST /api/v1/voice/calls/{call_id}/mute` (`mute_call`).
4. **End the call** — `POST /api/v1/voice/calls/{call_id}/hangup` (`hangup_call`).
5. **Observe outcomes** — control mutations return `202` with a `request_id`;
   the real result is delivered asynchronously via webhook events (e.g.
   `call.completed`). Reconcile with `GET /api/v1/events` (`list_webhook_events`)
   and redeliver with `POST /api/v1/events/{event_id}/redeliver` if you missed one.

## Conventions

- **Auth:** `x-api-key` header on every request.
- **Async:** control operations are asynchronous (`202` + `request_id`); watch webhooks for completion.
- **Errors:** branch on the stable `code` field (e.g. `call_not_live`,
  `transfer_in_progress`), not on the human `message`.
- **Retries:** `502`/`503`/`504` are transient ("please try again"); reuse the
  `request_id` to correlate retries.
