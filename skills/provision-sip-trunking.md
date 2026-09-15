---
name: provision-sip-trunking
description: Provision programmable SIP trunking with Teler — create a trunk, lock it down with an IP access-control list, and attach virtual numbers.
api: Teler Voice API
operations:
  - create_ip_acl
  - create_sip_trunk
  - list_sip_trunk_virtual_numbers
  - assign_virtual_numbers
  - list_sip_calls
---

# Provision SIP trunking

All requests go to `https://api.frejun.ai` with your secret key in the
`x-api-key` header.

## Steps

1. **Create an IP access-control list** — `POST /api/v1/sip/ip-acls`
   (`create_ip_acl`) with the allowed source IPs/credentials that may use the
   trunk. Returns an IP ACL id (`ip_acl_` reference).
2. **Create the SIP trunk** — `POST /api/v1/sip/trunks` (`create_sip_trunk`),
   referencing the `ip_acl_id` from step 1 (and a `secret_id` for auth
   credentials). Returns a trunk id (`st_` prefix).
3. **Attach virtual numbers** — assign numbers to the trunk with
   `POST /api/v1/virtual-numbers/assign` (`assign_virtual_numbers`), and confirm
   with `GET /api/v1/sip/trunks/{trunk_id}/virtual-numbers`
   (`list_sip_trunk_virtual_numbers`).
4. **Observe SIP calls** — `GET /api/v1/sip/calls` (`list_sip_calls`) and
   `GET /api/v1/sip/calls/{call_id}` (`retrieve_sip_call`) with cursor pagination
   (`cursor_after` / `limit`).

## Conventions

- **Auth:** `x-api-key` header on every request.
- **Pagination:** cursor-based — follow `next_cursor` into `cursor_after`.
- **Teardown is a hard delete:** `DELETE /api/v1/sip/trunks/{trunk_id}` and
  `DELETE /api/v1/sip/ip-acls/{ip_acl_id}` have no documented restore window;
  `unassign_virtual_numbers` is the inverse of `assign_virtual_numbers`.
- **Errors:** branch on the stable `code`/`type` fields, not on `message`.
