# Engineering Challenges

SeuLeilão is useful as an engineering project because the problem is not just a CRUD application. It involves unreliable inputs, documents, asynchronous processing, evolving rules and human judgment.

## Heterogeneous sources

Information about an opportunity may arrive through different sources and formats.

The system needs to normalize that information without losing where it came from.

**Engineering concern:** provenance, normalization and source-specific adapters.

## Changing information over time

Auction-related information can change.

Instead of treating the latest value as if it had always been true, the project preserves history where it matters.

**Engineering concern:** versioning and auditability.

## Documents and extracted information

Some relevant information may only exist inside documents.

Document acquisition and extraction can fail, require retries or need human review.

**Engineering concern:** asynchronous processing, failure handling and traceability.

## Conflicting or incomplete data

Different sources can disagree, or required information may be unavailable.

The application should not silently choose a value merely to keep processing.

**Engineering concern:** explicit unresolved states and review workflows.

## Long-running work

Collection, document processing and enrichment may take longer than an HTTP request should.

**Engineering concern:** Celery workers, retryable jobs and idempotent processing.

## Human-in-the-loop workflows

Some cases require judgment rather than deterministic automation.

The project models review as part of the product flow instead of treating manual intervention as an exception outside the system.

**Engineering concern:** review queues, decisions and audit trails.

## Product evolution

The domain is being learned while the software is built.

That makes premature abstractions and distributed architecture particularly risky.

**Engineering concern:** modularity, ADRs, vertical slices and iterative validation.

## Testing

Automated tests are used to protect deterministic behavior, processing flows and important boundaries while the system evolves.

The goal is not only regression prevention, but also making product and engineering assumptions executable and reviewable.
