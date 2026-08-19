---
name: opal-upload-and-reference-assets
description: >-
  Get creative files into Opal's asset library — direct upload or URL ingest — and attach them to
  content as asset references with usage rights. Use when an agent needs to supply artwork to a plan.
api: Opal API v2
spec: openapi/opal-v2-openapi.yml
base_url: https://login.ouropal.com
generated: '2026-08-13'
method: generated
source: openapi/opal-v2-openapi.yml
operations:
  - CreateAssetV2
  - GetAssetsV2
  - GetAssetV2
  - CreateUrlUploadV2
  - ReadUrlUploadsV2
  - GetUrlUploadV2
  - CreateAssetReferenceV1
  - ReadAssetReferencesV1
  - UpdateAssetReferenceV1
  - DeleteAssetReferenceV1
  - ReadAssetReferenceUsageRightOptionsV2
---

# Upload and reference assets in Opal

An **asset** is the stored file. An **asset reference** is the use of that file somewhere in a plan,
carrying its own metadata and usage rights. One asset can be referenced many times.

## Two ways in

- **Direct upload** — `CreateAssetV2` (`POST /assets/v2`). This operation takes the file metadata in
  request headers: `X-File-Name`, `X-File-Size` and `X-Mime-Type`. Send all three; they are declared
  in the spec, not optional decoration.
- **URL ingest** — `CreateUrlUploadV2` (`POST /assets/v2/url_uploads`) hands Opal a URL and lets it
  fetch the file. This is asynchronous: poll `GetUrlUploadV2`
  (`GET /assets/v2/url_uploads/{url_upload_id}`) until it resolves, and list in-flight ingests with
  `ReadUrlUploadsV2`. Prefer this for large files and for anything already hosted.

## Steps

1. Upload with whichever route fits, then confirm with `GetAssetV2` (`GET /assets/v2/{asset_id}`).
2. Check the available rights vocabulary first:
   `ReadAssetReferenceUsageRightOptionsV2` (`GET /api/v1/asset_references/usage_rights_options`).
   Use a value Opal returns; do not invent one.
3. Create the reference: `CreateAssetReferenceV1` (`POST /api/v1/asset_references`), pointing at the
   asset and the place it is used.
4. Read, correct or retire it: `ReadAssetReferencesV1`, `UpdateAssetReferenceV1`
   (`PATCH /api/v1/asset_references/{asset_reference_id}`), `DeleteAssetReferenceV1`.
5. Audit the library with `GetAssetsV2` (`GET /assets/v2`) — filter it; the Firehose Rule means an
   unfiltered read returns the whole accessible library.

## Rules that will bite you

- **Asset references live under `/api/v1/...`, not `/assets/v2/...`.** Two different path families,
  same workflow. Do not assume the version prefix.
- **URL ingest is async.** Treat the create call as accepted-not-done and poll. A `202` means
  queued.
- **Deleting a reference is not deleting the asset**, and vice versa — check what you are removing.
- **No idempotency keys.** A retried upload creates a second asset. Reconcile with `GetAssetsV2`
  before retrying.
- **Errors are JSON:API `errors[]`**; `404` may be an authorization failure per Opal's documented
  Obscurity principle.
