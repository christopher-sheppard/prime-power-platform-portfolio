# Project overview: settlement exception review

[README](../README.md) · [Build status](../BUILD_STATUS.md) · [Data model](DATA_MODEL.md) · [Acceptance scenarios](../tests/ACCEPTANCE.md)

**Stage: implementation in progress.** This document explains the intended design. Actual Microsoft solution exports and verified runtime evidence are still to be added to the repository.

## User need

An owner-operator reviewing settlement records needs a way to record an issue, inspect its original context and document a decision. A submitted form is only one stage: the user also needs to know whether the request was processed, rejected, deferred or interrupted.

The project explores that workflow with Power Apps for the review interface, Dataverse for durable records and Power Automate for processing. Chris Sheppard supplies the operating requirements; Hermes assists with implementation. Codex prepared the repository documentation.

## Proposed records and responsibilities

| Record | Purpose | Business rule |
|---|---|---|
| `ReviewItem` | The source-linked exception being examined | Retain original value, source reference and version |
| `ReviewDecision` | One intentional reviewer submission | Require a reason and identify repeated requests |
| `ProcessRun` | Durable processing state for a request | Preserve outcomes and enough identity to recover after interruption |

One item can have multiple decisions over time. A deliberate new decision gets a new request ID; retrying the same decision keeps its existing request ID. The [data model](DATA_MODEL.md) explains the proposed relationships and concurrency requirements.

The first version should accept customer code, city and state without requiring a street-address lookup. Customer codes remain text, and plants under the same company remain separate facilities. The demonstration uses fictional records and has no write connection to the private financial ledger.

## What a completed demonstration should show

| Scenario | Required visible evidence |
|---|---|
| Normal review | Queue item, original context, reasoned decision and durable processed outcome |
| Repeated submission | Existing request reused or resumed with no second processing effect |
| Stale source | Explicit conflict that preserves the newer source state |
| Interrupted processing | Controlled failure and recovery without duplicating the effect |
| Deferral or rejection | Preserved original values and decision history |
| Reproduction | Actual export imported and exercised with fictional seed records |

These are acceptance targets, not passed tests. Earlier supplied screenshots reported app publication and some submission checks, with the decision still **Submitted**. The September 28 Hermes update reports a native-designer Save denial (`FlowNotOriginalAuthor`); both drafts remain inactive and no successful processor run is verified. See [build status](../BUILD_STATUS.md) and the [sanitized checkpoint](../evidence/HERMES_CHECKPOINT_20260928.md) for the evidence boundary.

## Evidence package to add

Keep the actual solution version/hash, supported export and unpacked source, seed data, setup steps, dated expected/actual results, screenshots of the running app and relevant flow/storage outcomes together. Link each runtime result to the artifact version it tests. A dashboard screenshot alone cannot demonstrate duplicate protection or recovery.

Once those artifacts are available, this overview can become a completed implementation case study with measured results. At the current stage, it demonstrates business analysis and workflow design; it does not establish a deployed, reproducible Microsoft solution.
