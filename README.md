# Opal

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

Opal is a marketing planning and content calendar platform that gives marketing teams a single visual workspace to plan campaigns, build editorial and content calendars, manage creative workflows and approvals, and connect strategy to execution across channels and markets. It is used by enterprise brands such as Target, Starbucks, GM, and SAP, and pairs a unified planning calendar with a "Gem" AI co-pilot plus prebuilt integrations to Slack, Jira, Asana, Wrike, Workfront, Sprinklr, Khoros, Frame.io, Sprout Social, Formstack and Zapier. Opal does ship a real REST API: three OpenAPI 3.0 definitions — v2, v3 and an internal-facing Asgard BFF service — are served publicly from login.ouropal.com and cover stories, moments, content, boards, board objects, assets, asset references, labels, stamps, workflows, custom fields, presentations, rich-text documents and Gem chats. The v2 and v3 surfaces are JSON:API-compliant and authenticate with OAuth 2.0 authorization code (plus a client-credentials onboarding flow and a deprecated Session-Token header). The documentation is public, but API credentials are gated: Opal states access requires an active account or an NDA plus approval from Opal leadership, and OAuth client registration is a manual process handled by its integrations team.

**Areas:** Company · Consumer · Marketing · Content Planning · Marketing Calendar · Campaign Management · Collaboration · Software-as-a-Service · Content Marketing · Editorial Calendar · Workflows · Approvals

## Opal on APIs.io

Everything profiled for Opal is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/opal/](https://apis.io/providers/opal/)** — or go straight to one of the APIs or properties below.

### APIs (79)

- [Opal Accounts API](https://apis.io/apis/opal/opal-accounts-api/) — The Accounts API from Opal — 4 operation(s) for accounts.
- [Opal Activities API](https://apis.io/apis/opal/opal-activities-api/) — ## Activities Overview In Opal, "activities" encompass both things like someone adding an asset to content and also someone sending a chat message. In the…
- [Opal Annotations API](https://apis.io/apis/opal/opal-annotations-api/) — The Annotations API from Opal — 4 operation(s) for annotations.
- [Opal Asset Reference Options API](https://apis.io/apis/opal/opal-asset-reference-options-api/) — The Asset Reference Options API from Opal — 1 operation(s) for asset reference options.
- [Opal Asset Reference Usage Rights Options API](https://apis.io/apis/opal/opal-asset-reference-usage-rights-options-api/) — The Asset Reference Usage Rights Options API from Opal — 1 operation(s) for asset reference usage rights options.
- [Opal Asset References API](https://apis.io/apis/opal/opal-asset-references-api/) — ## Asset References Overview In Opal, you create `assets` to represent files uploaded to the platform and `asset_references` to surface those assets for use…
- [Opal Assets API](https://apis.io/apis/opal/opal-assets-api/) — ## Assets Overview Assets represent images, videos, PDFs, and any other file uploads. Any upload to the Opal platform must start with an `asset`. Some…
- [Opal Block Connectors API](https://apis.io/apis/opal/opal-block-connectors-api/) — ## Block Connectors Block connectors link blocks to views. A view can contain many blocks via block connectors. A block can also belong to many views via…
- [Opal Block Custom Field Values API](https://apis.io/apis/opal/opal-block-custom-field-values-api/) — The Block Custom Field Values API from Opal — 2 operation(s) for block custom field values.
- [Opal Block Duplication API](https://apis.io/apis/opal/opal-block-duplication-api/) — The Block Duplication API from Opal — 2 operation(s) for block duplication.
- [Opal Blocks API](https://apis.io/apis/opal/opal-blocks-api/) — The Blocks API from Opal — 5 operation(s) for blocks.
- [Opal Board Collaborators API](https://apis.io/apis/opal/opal-board-collaborators-api/) — ## Board Collaborators Overview Board Collaborators allow opal users to add other users as a collaborator on their **private** Boards. This allows the…
- [Opal Board Columns API](https://apis.io/apis/opal/opal-board-columns-api/) — The Board Columns API from Opal — 2 operation(s) for board columns.
- [Opal Board Duplication API](https://apis.io/apis/opal/opal-board-duplication-api/) — The Board Duplication API from Opal — 2 operation(s) for board duplication.
- [Opal Board Objects API](https://apis.io/apis/opal/opal-board-objects-api/) — ## Overview - **[Board](#tag/Boards/operation/CreateBoardV3)**: A board is the parent container and encapsulates its Board Objects and Board Object…
- [Opal Board Standard Columns API](https://apis.io/apis/opal/opal-board-standard-columns-api/) — The Board Standard Columns API from Opal — 1 operation(s) for board standard columns.
- [Opal Board User Settings API](https://apis.io/apis/opal/opal-board-user-settings-api/) — The Board User Settings API from Opal — 1 operation(s) for board user settings.
- [Opal Boards API](https://apis.io/apis/opal/opal-boards-api/) — The Boards API from Opal — 5 operation(s) for boards.
- [Opal Brand Settings API](https://apis.io/apis/opal/opal-brand-settings-api/) — The Brand Settings API from Opal — 2 operation(s) for brand settings.
- [Opal Brands API](https://apis.io/apis/opal/opal-brands-api/) — The Brands API from Opal — 1 operation(s) for brands.
- [Opal Budgets API](https://apis.io/apis/opal/opal-budgets-api/) — The Budgets API from Opal — 2 operation(s) for budgets.
- [Opal Bulk Operations API](https://apis.io/apis/opal/opal-bulk-operations-api/) — ## Bulk Operations A Bulk Operation represents a number of individual actions to be performed. ### Terms - **``Operation ID``**: A unique string identifier…
- [Opal Categories API](https://apis.io/apis/opal/opal-categories-api/) — ## Overview Categories are in a tree: a given category has zero or more ancestors and zero or more descendants. The tree is built by recursively following…
- [Opal Category Types API](https://apis.io/apis/opal/opal-category-types-api/) — The Category Types API from Opal — 2 operation(s) for category types.
- [Opal Channels API](https://apis.io/apis/opal/opal-channels-api/) — The Channels API from Opal — 1 operation(s) for channels.
- [Opal Charts API](https://apis.io/apis/opal/opal-charts-api/) — The Charts API from Opal — 3 operation(s) for charts.
- [Opal Checkpoints API](https://apis.io/apis/opal/opal-checkpoints-api/) — The Checkpoints API from Opal — 1 operation(s) for checkpoints.
- [Opal Content API](https://apis.io/apis/opal/opal-content-api/) — The Content API from Opal — 6 operation(s) for content.
- [Opal Content Schedules API](https://apis.io/apis/opal/opal-content-schedules-api/) — The Content Schedules API from Opal — 2 operation(s) for content schedules.
- [Opal Custom Field Colors API](https://apis.io/apis/opal/opal-custom-field-colors-api/) — The Custom Field Colors API from Opal — 1 operation(s) for custom field colors.
- [Opal Custom Field Options API](https://apis.io/apis/opal/opal-custom-field-options-api/) — The Custom Field Options API from Opal — 1 operation(s) for custom field options.
- [Opal Custom Field Types API](https://apis.io/apis/opal/opal-custom-field-types-api/) — The Custom Field Types API from Opal — 1 operation(s) for custom field types.
- [Opal Custom Fields API](https://apis.io/apis/opal/opal-custom-fields-api/) — ## Custom Fields Overview Custom Fields let you create custom inputs, the value of which can then be associated with a Moment, and allow your users to track…
- [Opal Delivery Records API](https://apis.io/apis/opal/opal-delivery-records-api/) — The Delivery Records API from Opal — 1 operation(s) for delivery records.
- [Opal Experimental API](https://apis.io/apis/opal/opal-experimental-api/) — The Experimental API from Opal — 2 operation(s) for experimental.
- [Opal Filter Sets API](https://apis.io/apis/opal/opal-filter-sets-api/) — The Filter Sets API from Opal — 2 operation(s) for filter sets.
- [Opal Gem Chats API](https://apis.io/apis/opal/opal-gem-chats-api/) — The Gem Chats API from Opal — 2 operation(s) for gem chats.
- [Opal Gem Files API](https://apis.io/apis/opal/opal-gem-files-api/) — The Gem Files API from Opal — 2 operation(s) for gem files.
- [Opal In Market API](https://apis.io/apis/opal/opal-in-market-api/) — The In Market API from Opal — 1 operation(s) for in market.
- [Opal Key Dates API](https://apis.io/apis/opal/opal-key-dates-api/) — The Key Dates API from Opal — 2 operation(s) for key dates.
- [Opal Label Sets API](https://apis.io/apis/opal/opal-label-sets-api/) — The Label Sets API from Opal — 1 operation(s) for label sets.
- [Opal Labels API](https://apis.io/apis/opal/opal-labels-api/) — ## Labels Overview In Opal, Labels are a useful way of categorizing resources to be filtered or grouped. ### Label Inheritance Labels follow StoryFirst…
- [Opal Messages API](https://apis.io/apis/opal/opal-messages-api/) — The Messages API from Opal — 2 operation(s) for messages.
- [Opal Moment Assignees API](https://apis.io/apis/opal/opal-moment-assignees-api/) — The Moment Assignees API from Opal — 2 operation(s) for moment assignees.
- [Opal Moment Custom Fields API](https://apis.io/apis/opal/opal-moment-custom-fields-api/) — The Moment Custom Fields API from Opal — 2 operation(s) for moment custom fields.
- [Opal Moment Duplication API](https://apis.io/apis/opal/opal-moment-duplication-api/) — The Moment Duplication API from Opal — 2 operation(s) for moment duplication.
- [Opal Moment Schedules API](https://apis.io/apis/opal/opal-moment-schedules-api/) — The Moment Schedules API from Opal — 2 operation(s) for moment schedules.
- [Opal Moments API](https://apis.io/apis/opal/opal-moments-api/) — The Moments API from Opal — 6 operation(s) for moments.
- [Opal Onboarding API](https://apis.io/apis/opal/opal-onboarding-api/) — ## Onboarding Overview Unlike many other Opal endpoints, the Onboarding endpoints are only accessible via a special OAuth scope that is not currently…
- [Opal Phase Items API](https://apis.io/apis/opal/opal-phase-items-api/) — The Phase Items API from Opal — 2 operation(s) for phase items.
- [Opal Planning Status API](https://apis.io/apis/opal/opal-planning-status-api/) — The Planning Status API from Opal — 1 operation(s) for planning status.
- [Opal Plans API](https://apis.io/apis/opal/opal-plans-api/) — The Plans API from Opal — 1 operation(s) for plans.
- [Opal Post Types API](https://apis.io/apis/opal/opal-post-types-api/) — The Post Types API from Opal — 1 operation(s) for post types.
- [Opal Presentation Themes API](https://apis.io/apis/opal/opal-presentation-themes-api/) — Workspace brand presentation themes
- [Opal Privacy API](https://apis.io/apis/opal/opal-privacy-api/) — The Privacy API from Opal — 1 operation(s) for privacy.
- [Opal Reactions API](https://apis.io/apis/opal/opal-reactions-api/) — The Reactions API from Opal — 3 operation(s) for reactions.
- [Opal Rich Text Documents API](https://apis.io/apis/opal/opal-rich-text-documents-api/) — ## Overview ### Client libraries and document formats Rich Text Document endpoints can accept documents in arbitrary formats. The `client_library` attribute…
- [Opal Rich Texts API](https://apis.io/apis/opal/opal-rich-texts-api/) — The Rich Texts API from Opal — 2 operation(s) for rich texts.
- [Opal Search API](https://apis.io/apis/opal/opal-search-api/) — The Search API from Opal — 1 operation(s) for search.
- [Opal Services API](https://apis.io/apis/opal/opal-services-api/) — The Services API from Opal — 1 operation(s) for services.
- [Opal Smart Blocks API](https://apis.io/apis/opal/opal-smart-blocks-api/) — The Smart Blocks API from Opal — 2 operation(s) for smart blocks.
- [Opal Stamps API](https://apis.io/apis/opal/opal-stamps-api/) — ## Stamps Overview In Opal, a Stamp acts as a pre-configured template for creating `moment`s or `content`. The `stamp_type` attribute specifies if the stamp…
- [Opal Stories API](https://apis.io/apis/opal/opal-stories-api/) — The Stories API from Opal — 6 operation(s) for stories.
- [Opal Stories V1 API](https://apis.io/apis/opal/opal-stories-v1-api/) — The Stories V1 API from Opal — 1 operation(s) for stories v1.
- [Opal URL Previews API](https://apis.io/apis/opal/opal-url-previews-api/) — The URL Previews API from Opal — 1 operation(s) for url previews.
- [Opal Url Uploads API](https://apis.io/apis/opal/opal-url-uploads-api/) — The Url Uploads API from Opal — 2 operation(s) for url uploads.
- [Opal User Domain Views API](https://apis.io/apis/opal/opal-user-domain-views-api/) — The User Domain Views API from Opal — 1 operation(s) for user domain views.
- [Opal User Groups API](https://apis.io/apis/opal/opal-user-groups-api/) — The User Groups API from Opal — 5 operation(s) for user groups.
- [Opal Users API](https://apis.io/apis/opal/opal-users-api/) — The Users API from Opal — 6 operation(s) for users.
- [Opal View Colors API](https://apis.io/apis/opal/opal-view-colors-api/) — The View Colors API from Opal — 1 operation(s) for view colors.
- [Opal View Columns API](https://apis.io/apis/opal/opal-view-columns-api/) — The View Columns API from Opal — 2 operation(s) for view columns.
- [Opal View Standard Columns API](https://apis.io/apis/opal/opal-view-standard-columns-api/) — The View Standard Columns API from Opal — 1 operation(s) for view standard columns.
- [Opal Views API](https://apis.io/apis/opal/opal-views-api/) — The Views API from Opal — 3 operation(s) for views.
- [Opal Workflow Assignments API](https://apis.io/apis/opal/opal-workflow-assignments-api/) — The Workflow Assignments API from Opal — 2 operation(s) for workflow assignments.
- [Opal Workflow Contexts API](https://apis.io/apis/opal/opal-workflow-contexts-api/) — The Workflow Contexts API from Opal — 1 operation(s) for workflow contexts.
- [Opal Workflow Responses API](https://apis.io/apis/opal/opal-workflow-responses-api/) — The Workflow Responses API from Opal — 2 operation(s) for workflow responses.
- [Opal Workflow Stages API](https://apis.io/apis/opal/opal-workflow-stages-api/) — The Workflow Stages API from Opal — 2 operation(s) for workflow stages.
- [Opal Workflows API](https://apis.io/apis/opal/opal-workflows-api/) — ## Workflows Overview In Opal, a workflow is an arrangement of tasks and approvals required to progress through the lifecycle of a StoryFirst resource.…
- [Opal Workspaces API](https://apis.io/apis/opal/opal-workspaces-api/) — The Workspaces API from Opal — 3 operation(s) for workspaces.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [opal-mcp.yml](https://apis.io/servers/opal/opal-mcp-yml/)

#### Collections (3)

Postman and Open Collection request collections.

- [Asgard BFF API](https://apis.io/collections/opal/open-opal-asgard-bff/)
- [Opal API](https://apis.io/collections/opal/open-opal-v2/)
- [Opal API (⚠️  WIP)](https://apis.io/collections/opal/open-opal-v3/)

#### Overlays (3)

OpenAPI overlays, including conversational phrasing for each operation.

- [Opal Asgard Bff Overlay](https://apis.io/overlays/opal/opal-asgard-bff-overlay/)
- [Opal V2 Overlay](https://apis.io/overlays/opal/opal-v2-overlay/)
- [Opal V3 Overlay](https://apis.io/overlays/opal/opal-v3-overlay/)

#### Security (3)

Authentication, trust centre, and vulnerability disclosure.

- [Opal Authentication](https://apis.io/security/opal/opal-authentication/)
- [Opal Domain Security](https://apis.io/security/opal/opal-domain-security/)
- [Opal Trust Center](https://apis.io/security/opal/opal-trust-center/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Opal Scopes](https://apis.io/scopes/opal/opal-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Opal Plans Pricing](https://apis.io/plans/opal/opal-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Opal Rate Limits](https://apis.io/rate-limits/opal/opal-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.workwithopal.com)
- [Documentation](https://login.ouropal.com/api/documentation)
- [Getting started](https://help.workwithopal.com/article/17imdltzi1-opal-api)
- [API reference](https://login.ouropal.com/api/documentation)
- [Pricing](https://workwithopal.com/pricing/)
- [Support](https://help.workwithopal.com/)
- [Changelog](https://help.workwithopal.com/article/42ysdzfa2y-change-log)
- [Blog](https://workwithopal.com/about/blog/)
- [Compliance](https://workwithopal.com/security/)
- [Terms of service](https://workwithopal.com/terms-of-service/)
- [Privacy policy](https://workwithopal.com/privacy-policy/)

## API Evangelist rating

**Kin Score 49.8** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 71.4 |
| Contract quality | 49.9 |
| Contract governance | 4.5 |
| Operational transparency | 23.7 |
| Developer ergonomics | 58.9 |
| Access clarity | 53.9 |

**Agent readiness 30.8** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | negotiable (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | documented (partial credit) |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | partial |
| Operation Distinctiveness | mostly |

**Regulatory alignment 39.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/opal/](https://apis.io/providers/opal/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Opal: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/opal/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
