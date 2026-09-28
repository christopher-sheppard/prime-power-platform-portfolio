# Build status

Updated September 28, 2026 from the operator-supplied Hermes screenshot and unsent support draft. These are reported observations; no new Microsoft runtime session was independently executed during this repository update.

**Current blocker:** native-designer Save returns `FlowNotOriginalAuthor` / XRM Unauthorized `0x80060467`. The reported metadata and original-author denial are inconsistent from the maker's perspective, but the underlying cause is not established. See the [sanitized diagnostic checkpoint](evidence/HERMES_CHECKPOINT_20260928.md).

| Component | Evidence available | Current status / next evidence |
|---|---|---|
| Canvas app | Earlier Hermes report of compilation and publication; latest report says app/checkpoints preserved | Reported checkpoint; actual export and dated runtime walkthrough needed |
| Input validation | Earlier report that invalid submission created zero decisions | Not independently reproduced; storage counts and reproduction steps needed |
| Duplicate submission | Earlier report that a repeated request reused decision IDs | Submission checkpoint only; no proof of duplicate-free downstream processing |
| Dataverse | Proposed entity model and reported read-only ownership/connection checks | Actual schema/export and fictional seed fixture needed |
| Cloud-flow Save | Reported connection-warning repair followed by original-author denial; server modification timestamp unchanged | Blocked; neither target nor earlier draft enabled |
| Cloud-flow processing | No successful processor run verified | Blocked behind successful Save and definition review |
| Final acceptance | Scenarios documented in tests/ACCEPTANCE.md | End-to-end cases unexecuted here; not passed |
| Reproduction | Documentation scaffold only | Supported export and successful import into a suitable development environment needed |

The latest reported decision is Submitted. Do not label it processed or applied without a durable processing outcome. No test result in this repository establishes a change to the real financial ledger.

An escalation draft exists but has not been sent. Preserve app, records and inactive flow drafts while an authorized administrator or Microsoft support investigates. The raw draft and terminal screenshot contain private identifiers and are excluded from this repository.

Environment, tenant, connection identifiers and authentication state belong in private local configuration. The repository currently supports workflow design and a documented troubleshooting checkpoint, not a completed Microsoft automation claim.
