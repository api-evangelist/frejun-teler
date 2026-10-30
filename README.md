# FreJun Teler

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

FreJun Teler is a developer-first programmable voice/telephony API (CPaaS) that handles carriers, phone numbers, and real-time audio streaming so developers can connect AI models (STT/LLM/TTS) to live phone calls. It offers real-time bidirectional audio over WebSocket (L16/8000 Hz, sub-250ms latency) and programmable SIP trunking, with webhook event delivery and official Python (teler) and Node (@frejun/teler) SDKs.

**Areas:** programmable voice API · voice AI infrastructure · CPaaS · SIP Trunking · telephony API · real-time media streaming · WebSocket audio · Call Automation · conversational AI infrastructure

## FreJun Teler on APIs.io

Everything profiled for FreJun Teler is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/frejun-teler/](https://apis.io/providers/frejun-teler/)** — or go straight to one of the APIs or properties below.

### APIs (12)

- [FreJun Teler Events API](https://apis.io/apis/frejun-teler/frejun-teler-events-api/) — Inspect the webhook events Teler generated for your account and redeliver any that your endpoint missed.
- [FreJun Teler Secrets API](https://apis.io/apis/frejun-teler/frejun-teler-secrets-api/) — Manage secret API keys used for authenticating requests. Create, rotate, and delete secrets — rotate periodically and keep them server-side.
- [FreJun Teler SIP / Calls API](https://apis.io/apis/frejun-teler/frejun-teler-sip-calls-api/) — Read calls that arrived or left over your SIP trunks (`st_`).
- [FreJun Teler SIP / IP Access Control Lists API](https://apis.io/apis/frejun-teler/frejun-teler-sip-ip-access-control-lists-api/) — Named sets of source IPs or CIDR networks (`acl_`) that SIP trunks with `authentication_type: IP` authorise against. Attach one to many trunks and update it…
- [FreJun Teler SIP / Trunks API](https://apis.io/apis/frejun-teler/frejun-teler-sip-trunks-api/) — SIP trunks connect Teler to your upstream carrier or PBX. Create, configure, and manage your trunks, or inspect which virtual numbers are assigned to each one.
- [FreJun Teler Utilities API](https://apis.io/apis/frejun-teler/frejun-teler-utilities-api/) — Fetch short-lived, signed download URLs for call recordings.
- [FreJun Teler Virtual Numbers API](https://apis.io/apis/frejun-teler/frejun-teler-virtual-numbers-api/) — Phone numbers that Teler provisions for your account. List, assign to a voice app or SIP trunk, unassign, or update individual numbers.
- [FreJun Teler Voice / Apps API](https://apis.io/apis/frejun-teler/frejun-teler-voice-apps-api/) — Voice apps are the configuration context for calls — they define webhook URLs, flows, and channel limits. Create and manage your voice apps here.
- [FreJun Teler Voice / Call Controls API](https://apis.io/apis/frejun-teler/frejun-teler-voice-call-controls-api/) — Act on a live call in real time — hang up, mute, send DTMF, or play audio. These actions are accepted asynchronously and return `202` with a `request_id`.
- [FreJun Teler Voice / Calls API](https://apis.io/apis/frejun-teler/frejun-teler-voice-calls-api/) — Place outbound calls and read call state. A **call** (`cs_`) is the top-level session; each party on it is a **leg** (`cl_`).
- [FreJun Teler Voice / Calls (legacy) API](https://apis.io/apis/frejun-teler/frejun-teler-voice-calls-legacy-api/) — Deprecated endpoints kept for backwards compatibility. Prefer the **Voice / Calls** endpoints for all new integrations.
- [FreJun Teler Voice / Operations API](https://apis.io/apis/frejun-teler/frejun-teler-voice-operations-api/) — Higher-level, multi-step operations on a live call, such as transferring it to a new destination.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Frejun Teler Webhooks](https://apis.io/asyncapis/frejun-teler/frejun-teler-webhooks/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [frejun-teler-mcp.yml](https://apis.io/servers/frejun-teler/frejun-teler-mcp-yml/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Frejun Teler Openapi Overlay](https://apis.io/overlays/frejun-teler/frejun-teler-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Frejun Teler Authentication](https://apis.io/security/frejun-teler/frejun-teler-authentication/)
- [Frejun Teler Domain Security](https://apis.io/security/frejun-teler/frejun-teler-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Frejun Teler Plans Pricing](https://apis.io/plans/frejun-teler/frejun-teler-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Frejun Teler Rate Limits](https://apis.io/rate-limits/frejun-teler/frejun-teler-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.frejun.ai)
- [Documentation](https://frejun.com/docs/teler/)
- [API reference](https://api.frejun.ai/redoc)
- [Pricing](https://frejun.com/teler/pricing/)
- [Sign up](https://platform.frejun.ai/signup)
- [Blog](https://frejun.com/teler-blog/)
- [Terms of service](https://frejun.com/terms/)
- [Privacy policy](https://frejun.com/privacy-policy/)
- [GitHub](https://github.com/frejun-tech)
- [Status](https://frejun.statuspage.io)

## API Evangelist rating

**Kin Score 40.8** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 64.0 |
| Contract governance | 4.5 |
| Operational transparency | 34.2 |
| Developer ergonomics | 45.8 |
| Access clarity | 22.4 |

**Agent readiness 49.8** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 17.5** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/frejun-teler/](https://apis.io/providers/frejun-teler/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for FreJun Teler: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/frejun-teler/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
