---
type: Policy
title: Synthetic Access Review Policy
description: A synthetic policy requiring periodic review of access to example business systems.
resource: ../sources/access-review-policy-source.md
---
# Source Object

| Field | Value |
| --- | --- |
| Canonical JSON source object | [policy.example.json](../../../../examples/schema-examples/policy.example.json) |
| Stable identifier | `policy-access-review-synthetic` |
| Object type | `policy` |

# Authority

| Field | Value |
| --- | --- |
| Authoritative source | Synthetic Policy Committee |
| Source artifact | [access-review-policy-source.md](../sources/access-review-policy-source.md) |

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
| Owner | `owner-governance-office-synthetic` |
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
| Handling notes | Synthetic public reference policy. Do not treat as operating guidance. |

# Provenance

| Field | Value |
| --- | --- |
| Created by | `author-public-reference-synthetic` |
| Created date | `2026-01-01` |
| Method | `synthetic_authoring` |
| Change summary | Initial synthetic policy example. |
| Last reviewed date | `2026-06-30` |

# Relationships

Requires: [Synthetic Quarterly Access Review Control](../controls/control-quarterly-access-review-synthetic.md).

The related control is represented in the source object as a typed relationship. OKF v0.1 can express the relationship as markdown text or as a link when the target concept exists in the same bundle, but the relationship type is not a standard OKF field.

# Assertions

| Assertion ID | Predicate | Object | Confidence |
| --- | --- | --- | --- |
| `assertion-access-review-required-synthetic` | requires review frequency | quarterly | declared |

# Evidence

| Evidence ID | Summary | Source artifact |
| --- | --- | --- |
| `evidence-access-review-policy-summary-synthetic` | Synthetic policy approval note for the example record. | [access-review-policy-source.md](../sources/access-review-policy-source.md#synthetic-approval-note) |

# Policy Content

Policy category: `access_management`.

Policy statement: Access to synthetic customer record systems must be reviewed on a recurring schedule.

Exception process: Exceptions require synthetic owner approval and a dated review note.

# Obligations

| Obligation ID | Statement | Applies To | Assertion IDs |
| --- | --- | --- | --- |
| `obligation-quarterly-access-review-synthetic` | Review privileged and standard access to synthetic customer record systems at least quarterly. | `system-customer-directory-synthetic` | `assertion-access-review-required-synthetic` |

# Mapping Notes

The frontmatter uses only OKF v0.1 standard fields: `type`, `title`, `description`, and `resource`. Other source fields are preserved in markdown body sections because OKF v0.1 does not define standard fields for authority, permissions, provenance, lifecycle state, typed relationships, assertions, evidence IDs, or obligations.

# Citations

[1] [Canonical JSON policy source](../../../../examples/schema-examples/policy.example.json)

[2] [Synthetic source artifact](../sources/access-review-policy-source.md)

[3] [Synthetic evidence artifact](../sources/access-review-policy-source.md#synthetic-approval-note)
