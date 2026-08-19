---
name: opal-plan-a-campaign
description: >-
  Create a campaign story in Opal and hang scheduled moments off it, then read the plan back.
  Use when an agent needs to put a campaign on a marketing team's Opal calendar.
api: Opal API v2
spec: openapi/opal-v2-openapi.yml
base_url: https://login.ouropal.com
generated: '2026-08-13'
method: generated
source: openapi/opal-v2-openapi.yml
operations:
  - CreateStoryV2
  - ReadStoriesV2
  - ReadStoryV2
  - UpdateStoryV2
  - CreateMomentV2
  - ReadMomentsV2
  - ReadMomentV2
  - UpdateMomentV2
  - DeleteMomentV2
---

# Plan a campaign in Opal

A **story** is the campaign container. **Moments** are the dated things that happen inside it and
are what appears on the marketing calendar. This skill creates one story and its moments.

## Before you start

- Get an OAuth 2.0 access token: authorize at `https://login.ouropal.com/oauth2/auth`, exchange the
  code at `https://login.ouropal.com/oauth2/token`, then send `Authorization: Bearer <token>`.
  Ask for the `offline_access` scope if you need a refresh token. Tokens expire in 3600 seconds.
- Send `Accept: application/vnd.api+json` — stories and moments are JSON:API resources.
- Opal registers OAuth clients manually through its integrations team. If you do not already have a
  client id and secret, stop: there is no self-serve path.

## Steps

1. **Check what already exists.** `ReadStoriesV2` (`GET /stories/v2`). Narrow with `filter[...]`,
   `sort` and `page[offset]` / `page[limit]` — Opal's documented Firehose Rule means an unfiltered
   read returns everything the authenticated user can see, which on an enterprise workspace is a
   lot. Do not skip the filter.
2. **Create the story.** `CreateStoryV2` (`POST /stories/v2`) with a JSON:API document whose
   `data.type` is the story resource and whose `attributes` carry the campaign name and dates.
   Read the request body schema in `openapi/opal-v2-openapi.yml#CreateStoryV2` for the exact
   members — do not guess attribute names.
3. **Read it back.** `ReadStoryV2` (`GET /stories/v2/{story_id}`) and keep the returned `id`.
4. **Add each moment.** `CreateMomentV2` (`POST /moments/v2`), relating each moment to the story id
   from step 3. Repeat per dated beat of the campaign.
5. **Verify the plan.** `ReadMomentsV2` (`GET /moments/v2`) filtered to the story, or `ReadMomentV2`
   per id.
6. **Adjust.** `UpdateMomentV2` (`PATCH /moments/v2/{moment_id}`) to move or rename a moment,
   `UpdateStoryV2` (`PATCH /stories/v2/{story_id}`) for the campaign itself, `DeleteMomentV2`
   (`DELETE /moments/v2/{moment_id}`) to remove one.

## Rules that will bite you

- **There are no idempotency keys.** Opal publishes none. If `CreateStoryV2` times out, do not
  blindly retry — `ReadStoriesV2` first and match on the attributes you sent, or you will create a
  duplicate campaign.
- **A 404 does not mean "not there".** Opal's published Obscurity principle returns
  `404 Not Found` instead of `403 Forbidden` for many authorization failures. Treat a 404 on a
  resource you just created as a permission problem, not a missing record.
- **Errors are JSON:API, not RFC 9457.** Parse `errors[]` and read `errors[].detail` and
  `errors[].code`; `errors[].status` is the only required member. A `422` means the body parsed but
  is semantically wrong.
- **No published rate limits.** Nothing tells you when to back off. Pace bulk creation yourself and
  retry `5xx` with exponential backoff.
- **Prefer v2 over v3 here.** Opal states that where a resource exists in both versions you SHOULD
  use v2; v3 is documented as work in progress.
