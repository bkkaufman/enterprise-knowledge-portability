# Versioning And Supersession

Portable knowledge should preserve version history instead of replacing old records in place. This matters when policy obligations, control expectations, jurisdictions, or effective dates change over time.

## Pattern

Records include `effective_from`, `effective_to`, `supersedes`, and `superseded_by`. A relationship can also express that one record supersedes another.

## Why It Matters

Downstream systems may need different answers depending on time. A workflow tool may need the current rule, an audit review may need the rule that was effective during a past period, and an AI assistant may need to explain why a newer record replaced an older one.

## Public Boundary

The supersession example is synthetic and intentionally simple. It does not model a real policy lifecycle, approval workflow, retention schedule, or regulatory interpretation process.

