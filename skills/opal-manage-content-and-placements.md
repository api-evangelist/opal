---
name: opal-manage-content-and-placements
description: >-
  Create content in Opal, attach it to a channel placement, and read or retire it. Use when an agent
  needs to put a specific post, email or asset into a channel slot on an Opal plan.
api: Opal API v2
spec: openapi/opal-v2-openapi.yml
base_url: https://login.ouropal.com
generated: '2026-08-13'
method: generated
source: openapi/opal-v2-openapi.yml
operations:
  - ReadContentsV2
  - CreateContentV2
  - ReadContentV2
  - UpdateContentV2
  - DeleteContentV2
  - CreatePostPlacementV2
  - PutPostPlacementV2
  - DeletePostPlacementV2
  - ReadPlacementsV0
  - ReadAccountsV2
---

# Manage content and channel placements in Opal

**Content** is the actual thing being published. A **placement** binds that content to a channel
account (a social profile, an email programme, a site). Content without a placement sits in the
plan but is not routed anywhere.

## Steps

1. **Find the target account and its placements.** `ReadAccountsV2` (`GET /accounts/v2`) to list
   channel accounts, then `ReadPlacementsV0` (`GET /accounts/{account_id}/placements`) for the
   placements available on one.
2. **Create the content.** `CreateContentV2` (`POST /content/v2`). The body schema is in
   `openapi/opal-v2-openapi.yml#CreateContentV2`; content is related to the moment it belongs to.
3. **Read it back.** `ReadContentV2` (`GET /content/v2/{content_id}`) and hold the id.
4. **Attach the placement.** `CreatePostPlacementV2`
   (`POST /content/v2/{content_id}/placements/{placement_id}`). Use `PutPostPlacementV2`
   (`PUT /content/v2/{content_id}/placements/{placement_id}`) to replace the binding wholesale.
5. **Edit or retire.** `UpdateContentV2` (`PATCH /content/v2/{content_id}`),
   `DeletePostPlacementV2` (`DELETE /content/v2/{content_id}/placements`) to clear placements, and
   `DeleteContentV2` (`DELETE /content/v2/{content_id}`) to remove the content itself.
6. **Audit.** `ReadContentsV2` (`GET /content/v2`) with `filter[...]` and `page[limit]`.

## Rules that will bite you

- **Check the category before you set `Accept`.** Content and placements sit across Opal's JSON:API
  and "Other" categories. JSON:API endpoints want `application/vnd.api+json`; "Other" endpoints want
  `application/json` and MUST be parsed as generic JSON even when the body looks JSON:API-shaped.
  Opal warns that `application/json` support MAY disappear from a JSON:API endpoint at any time.
- **`PUT` here is a replace, not a merge.** `PutPostPlacementV2` overwrites; `PATCH` on content is
  the partial update.
- **409 means conflicting state**, usually a duplicate association. Re-read before retrying.
- **No idempotency keys and no rate limits are published.** Sequence writes and reconcile by reading
  back rather than by retrying.
- **404 can mean "not allowed"** — see Opal's Obscurity principle in
  `conventions/opal-conventions.yml`.
