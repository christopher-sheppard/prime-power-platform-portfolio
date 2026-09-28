# Runtime acceptance evidence

No tests have been executed from this documentation scaffold. Hermes's screenshot reports are recorded separately in [BUILD_STATUS.md](../BUILD_STATUS.md).

**September 28 checkpoint:** processing acceptance is blocked by the reported native-designer Save denial, `FlowNotOriginalAuthor`. First establish successful Save and an updated server modification timestamp, review the saved definition, then run the synthetic scenarios below. Both drafts are reported inactive. Earlier input/duplicate-submission observations are not complete end-to-end processing results.

| Scenario | Required observation |
|---|---|
| Valid request | One linked decision, durable processed outcome, same result after reopening |
| Duplicate request | Same request ID returns/resumes the prior result; no second effect in storage or flow history |
| Missing reason | Input rejected; no accepted transition |
| Stale item version | Explicit conflict; newer source state preserved |
| Failure after write | Controlled interruption recovered without applying the effect twice |
| Defer/reject | Original values and previous decisions preserved |
| City/state only | Successful review without requiring a street address |
| Reproduction | Actual exported solution imports and runs with fictional seed data |

For each run record UTC timestamp, exported solution version/hash, scenario, expected/actual outcome, synthetic request ID and evidence path. Mark failed, blocked and untested cases explicitly. Keep environment and connection details in private local configuration.
