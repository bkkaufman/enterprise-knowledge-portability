---
type: Control
title: Synthetic Quarterly Access Review Control
description: A synthetic control for reviewing access to an example customer directory system.
resource: ../sources/quarterly-access-review-control-source.md
---
# Source Object

| Field | Value |
| --- | --- |
| Canonical JSON source object | [control.example.json](../../../../examples/schema-examples/control.example.json) |
| Stable identifier | `control-quarterly-access-review-synthetic` |
| Object type | `control` |

# Authority

| Field | Value |
| --- | --- |
| Authoritative source | Synthetic Control Library |
| Source artifact | [quarterly-access-review-control-source.md](../sources/quarterly-access-review-control-source.md) |

# Lifecycle

| Field | Value |
| --- | --- |
| Status | `active` |
| Version | `v1.0` |
| Effective date | `2026-01-01` |
| Expiration date | `null` |
| Supersedes | none |

# Governance

| Field | Value |
| --- | --- |
| Owner | `owner-access-operations-synthetic` |
| Steward | `steward-access-governance-synthetic` |
| Jurisdiction | `jurisdiction-global-synthetic` |
| Applicability | `capability-customer-record-management-synthetic`<br>`system-customer-directory-synthetic` |

# Permissions

| Field | Value |
| --- | --- |
| Classification | `public_example` |
| Access policy | `access-policy-public-example-synthetic` |
| Allowed uses | `read`<br>`validate`<br>`transform`<br>`publish_example` |
| Denied uses | `production_decisioning` |
| Handling notes | Synthetic control example. Do not use as a production control. |

# Provenance

| Field | Value |
| --- | --- |
| Created by | `author-public-reference-synthetic` |
| Created date | `2026-01-01` |
| Method | `synthetic_authoring` |
| Change summary | Initial synthetic control example. |
| Last reviewed date | `2026-06-30` |

# Relationships

Implements: [Synthetic Access Review Policy](../policies/policy-access-review-synthetic.md).

The related policy is represented in the source object as a typed relationship. OKF v0.1 can express the relationship as markdown text or as a link when the target concept exists in the same bundle, but the relationship type is not a standard OKF field.

# Incoming Relationships

| Relationship | Source object |
| --- | --- |
| Required by | [Synthetic Access Review Policy](../policies/policy-access-review-synthetic.md) |

This incoming relationship is derived from the policy record's canonical `requires` relationship. It is a navigation view and has no separate source record.

# Assertions

| Assertion ID | Predicate | Object | Confidence |
| --- | --- | --- | --- |
| `assertion-control-frequency-quarterly-synthetic` | operates every | quarter | declared |

# Evidence

| Evidence ID | Summary | Source artifact |
| --- | --- | --- |
| `evidence-access-review-sample-synthetic` | Synthetic evidence checklist showing the expected access review artifacts. | [quarterly-access-review-evidence.json](../sources/quarterly-access-review-evidence.json) |

# Control Content

| Field | Value |
| --- | --- |
| Control category | `access_review` |
| Control objective | Confirm that access to the synthetic customer directory remains appropriate. |
| Control type | `detective` |
| Operating frequency | `quarterly` |
| Systems | `system-customer-directory-synthetic` |
| Mapped obligations | `obligation-quarterly-access-review-synthetic` |

# Evidence Expectations

| Evidence Type | Expected Frequency | Retention Period |
| --- | --- | --- |
| Access review completion record | quarterly | two synthetic review cycles |

# Mapping Notes

The frontmatter uses only OKF v0.1 standard fields: `type`, `title`, `description`, and `resource`. Other source fields are preserved in markdown body sections because OKF v0.1 does not define standard fields for authority, permissions, provenance, lifecycle state, typed relationships, assertions, evidence IDs, control content, evidence expectations, or backlinks.

# Citations

[1] [Canonical JSON control source](../../../../examples/schema-examples/control.example.json)

[2] [Synthetic source artifact](../sources/quarterly-access-review-control-source.md)

[3] [Synthetic evidence artifact](../sources/quarterly-access-review-evidence.json)
