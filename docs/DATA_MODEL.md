# Proposed data model

Logical names below describe the intended model. Map them to the actual publisher prefix and exported schema after receiving the solution; do not rename deployed objects to match this document blindly.

| Entity | One row represents | Key fields |
|---|---|---|
| ReviewItem | One source-linked fictional exception | Stable external ID, issue type, source reference/excerpt, original value, text customer code, optional city/state, review state, version |
| ReviewDecision | One intentional reviewer decision | Decision ID, unique request ID, item lookup, proposed value/treatment, required reason, reviewer, timestamp, expected item version, processing status |
| ProcessRun | Durable processing state for one request | Unique request ID, linked decision/item, start/end, state, durable outcome reference, expected/resulting versions, failure/retry details |

One item may have many decisions. Retry of the same request must resume or return its existing result, not create a new decision/effect. A deliberately new decision receives a new request ID. Preserve prior decisions and original source values.

Use supported unique keys and concurrency controls in the implementation. Serial flow execution alone does not protect against other writers. Retain enough durable identity to recover after an item update but before success acknowledgement. Demonstrate the supported scope rather than claiming universal exactly-once execution.

Amounts, when needed in fictional examples, use an explicit unit and signed integer cents. Customer codes are text. Unknown values remain unknown. Street addresses are optional; separate facilities are not merged solely because they share a brand.
