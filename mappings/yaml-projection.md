# YAML Projection

This page shows how the policy object from [../examples/schema-examples/policy.example.json](../examples/schema-examples/policy.example.json) can be projected into YAML. The projection is easier to read and edit in some repositories, but it is still derived from the JSON reference representation used here.

```yaml
id: policy-access-review-synthetic
object_type: policy
title: Synthetic Access Review Policy
description: A synthetic policy requiring periodic review of access to example business systems.
status: active
version: v1.0
effective_date: 2026-01-01
expiration_date: null
supersedes: []
authoritative_source: Synthetic Policy Committee
source_uri: https://sources.example.invalid/policies/access-review
owner: owner-governance-office-synthetic
steward: steward-access-governance-synthetic
jurisdiction:
  - jurisdiction-global-synthetic
applicability:
  - capability-customer-record-management-synthetic
  - system-customer-directory-synthetic
classification: public_example
access_policy:
  policy_id: access-policy-public-example-synthetic
  allowed_uses:
    - read
    - validate
    - transform
    - publish_example
  denied_uses:
    - production_decisioning
  handling_notes: Synthetic public reference policy. Do not treat as operating guidance.
provenance:
  created_by: author-public-reference-synthetic
  created_date: 2026-01-01
  method: synthetic_authoring
  change_summary: Initial synthetic policy example.
last_reviewed_date: 2026-06-30
related_objects:
  - id: control-quarterly-access-review-synthetic
    relationship_type: requires
assertions:
  - assertion_id: assertion-access-review-required-synthetic
    predicate: requires review frequency
    object: quarterly
    confidence: declared
evidence:
  - evidence_id: evidence-access-review-policy-summary-synthetic
    summary: Synthetic policy approval note for the example record.
    uri: https://sources.example.invalid/evidence/access-review-policy-summary
policy_category: access_management
policy_statement: Access to synthetic customer record systems must be reviewed on a recurring schedule.
obligations:
  - obligation_id: obligation-quarterly-access-review-synthetic
    statement: Review privileged and standard access to synthetic customer record systems at least quarterly.
    applies_to:
      - system-customer-directory-synthetic
    assertion_ids:
      - assertion-access-review-required-synthetic
exception_process: Exceptions require synthetic owner approval and a dated review note.
```

## Preservation Profile

| Aspect | Projection Result |
| --- | --- |
| Stable identity | Direct mapping. The `id` value is unchanged. |
| Authority and source | Direct mapping. The same source fields can be preserved. |
| Provenance | Direct mapping if the nested provenance object is retained. |
| Permissions | Direct mapping if `classification` and `access_policy` are retained. |
| Versioning | Direct mapping for version, effective dates, expiration, and supersession fields. |
| Relationships | Direct mapping for inline `related_objects`; separate relationship files still need their own projection. |
| Assertions and evidence | Direct mapping if arrays are preserved without flattening. |
| Validation | Partial mapping. YAML can be converted to JSON for schema validation, but this release does not provide that converter. |

## Weakened Or Lost

YAML introduces parser and style choices that can affect dates, nulls, ordering, and quoting. A projection that drops nested objects for readability weakens permissions, provenance, assertions, and evidence. YAML also does not make semantics clearer by itself; it only changes the serialization.
