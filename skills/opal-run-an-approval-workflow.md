---
name: opal-run-an-approval-workflow
description: >-
  Drive an Opal approval workflow end to end — build the workflow and its stages, assign reviewers,
  record responses, and rewind when something is rejected. Use when an agent needs to route creative
  work for approval inside Opal.
api: Opal API v2
spec: openapi/opal-v2-openapi.yml
base_url: https://login.ouropal.com
generated: '2026-08-13'
method: generated
source: openapi/opal-v2-openapi.yml
operations:
  - ReadWorkflowsV2
  - CreateWorkflowsV2
  - ReadWorkflowV2
  - DuplicateWorkflowV2
  - RewindWorkflowV2
  - CreateStageV2
  - ReadStageV2
  - UpdateStageV2
  - DeleteStageV2
  - CreateContextV2
  - CreateAssignmentV2
  - ReadAssignmentsV2
  - ReadAssignmentV2
  - UpdateAssignmentV2
  - DeleteAssignmentV2
  - CreateResponseV2
  - ReadResponseV2
---

# Run an approval workflow in Opal

A **workflow** holds ordered **stages**. A **context** binds a workflow to the thing being
reviewed. An **assignment** puts a stage in front of a person. A **response** is that person's
decision.

## Steps

1. **Reuse before you build.** `ReadWorkflowsV2` (`GET /workflows/v2/workflows`) — most teams
   already have a template. `DuplicateWorkflowV2`
   (`POST /workflows/v2/workflows/{workflow_id}/duplicate`) clones one rather than re-authoring it.
2. **Create a workflow** if none fits: `CreateWorkflowsV2` (`POST /workflows/v2/workflows`).
3. **Add stages in order.** `CreateStageV2` (`POST /workflows/v2/stages`), one per review step.
   `UpdateStageV2` (`PATCH /workflows/v2/stages/{stage_id}`) to reorder or rename,
   `DeleteStageV2` to drop one.
4. **Bind the workflow to what is being reviewed.** `CreateContextV2`
   (`POST /workflows/v2/contexts`). Read the request schema at
   `openapi/opal-v2-openapi.yml#CreateContextV2` for the exact relationship members.
5. **Assign reviewers.** `CreateAssignmentV2` (`POST /workflows/v2/assignments`) per stage and
   assignee. Track them with `ReadAssignmentsV2` (`GET /workflows/v2/assignments`) and
   `ReadAssignmentV2`.
6. **Record decisions.** `CreateResponseV2` (`POST /workflows/v2/responses`); read one back with
   `ReadResponseV2` (`GET /workflows/v2/responses/{response_id}`).
7. **Handle a rejection.** `RewindWorkflowV2`
   (`PATCH /workflows/v2/workflows/{workflow_id}/rewind`) returns the workflow to an earlier stage.
   This is the sanctioned way back — do not delete and recreate the workflow.

## Rules that will bite you

- **Rewind is destructive to state.** It moves the whole workflow backwards; confirm with a human
  before calling it on anything a team is actively reviewing.
- **Responses are not idempotent.** Opal publishes no idempotency key. A retried `CreateResponseV2`
  can double-record a decision. Read assignments back to confirm before retrying.
- **Do not poll blindly.** There are no published rate limits and no `Retry-After` header, so an
  aggressive poll has no documented safe ceiling. Poll assignments on a slow interval.
- **Errors are JSON:API `errors[]`** — `422` for a semantically invalid body, `409` for conflicting
  state, `404` possibly meaning "not authorized" per Opal's Obscurity principle.
