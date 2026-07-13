# Conflict Resolution

Portable knowledge systems should preserve conflicts as explicit records until an authorized process resolves them.

## Pattern

Conflicting records can be marked with `lifecycle_status: conflicting` and connected with a `conflicts_with` relationship. The relationship should include rationale, source authority, permissions, and provenance.

## Why It Matters

Silent deduplication can hide important governance problems. If two records define different obligations for the same policy area, downstream systems should know that a conflict exists instead of choosing the newest or most convenient record automatically.

## Public Boundary

The conflict example is synthetic and does not define a real adjudication process, escalation path, legal interpretation, or control remediation workflow.

