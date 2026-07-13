# Markdown Projection

This page shows how the same policy object can be projected into human-readable Markdown. Markdown is useful for review and publication, but it weakens machine validation unless the structured fields are preserved elsewhere or embedded in a constrained block.

## Synthetic Access Review Policy

| Field | Value |
| --- | --- |
| ID | `policy-access-review-synthetic` |
| Object type | `policy` |
| Status | `active` |
| Version | `v1.0` |
| Effective date | `2026-01-01` |
| Expiration date | None |
| Supersedes | None |
| Authoritative source | Synthetic Policy Committee |
| Source artifact | [access-review-policy-source.md](okf/bundle/sources/access-review-policy-source.md) |
| Owner | `owner-governance-office-synthetic` |
| Steward | `steward-access-governance-synthetic` |
| Jurisdiction | `jurisdiction-global-synthetic` |
| Applicability | `capability-customer-record-management-synthetic`, `system-customer-directory-synthetic` |
| Classification | `public_example` |
| Last reviewed date | `2026-06-30` |

### Statement

Access to synthetic customer record systems must be reviewed on a recurring schedule.

### Obligation

`obligation-quarterly-access-review-synthetic`: Review privileged and standard access to synthetic customer record systems at least quarterly.

Applies to: `system-customer-directory-synthetic`

Assertion: `assertion-access-review-required-synthetic`

### Access Policy

Allowed uses: `read`, `validate`, `transform`, `publish_example`

Denied uses: `production_decisioning`

Handling notes: Synthetic public reference policy. Do not treat as operating guidance.

### Provenance

Created by: `author-public-reference-synthetic`

Created date: `2026-01-01`

Method: `synthetic_authoring`

Change summary: Initial synthetic policy example.

### Evidence

`evidence-access-review-policy-summary-synthetic`: Synthetic policy approval note for the example record.

Source artifact: [access-review-policy-source.md](okf/bundle/sources/access-review-policy-source.md#synthetic-approval-note)

### Related Objects

`control-quarterly-access-review-synthetic` has relationship type `requires`.

## Preservation Profile

| Aspect | Projection Result |
| --- | --- |
| Human readability | Direct mapping for readers. The policy is easier to review as a document. |
| Stable identity | Direct mapping if IDs are retained exactly. |
| Authority and source | Partial mapping. The fields are visible, but not schema constrained. |
| Provenance | Partial mapping. The content is present, but a parser may not reliably recover it. |
| Permissions | Partial mapping. Humans can read restrictions, but enforcement requires structured data. |
| Versioning | Partial mapping. Dates and supersession can be shown, but validation is weaker. |
| Relationships | Partial mapping. Inline prose can preserve intent, but graph traversal is weaker. |
| Assertions and evidence | Partial mapping. The information can be displayed, but machine use is weaker. |

## Weakened Or Lost

Markdown projections are prone to field omission, reordered sections, inconsistent labels, and prose edits that change meaning. They should not replace the reference object when an AI system or workflow needs governed context. Markdown is best treated as a reader view backed by structured records.
