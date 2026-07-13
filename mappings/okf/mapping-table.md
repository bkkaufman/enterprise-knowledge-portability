# OKF Mapping Table

This table maps the canonical JSON source objects at [../../examples/schema-examples/policy.example.json](../../examples/schema-examples/policy.example.json) and [../../examples/schema-examples/control.example.json](../../examples/schema-examples/control.example.json) to the OKF v0.1 Draft concept documents in [bundle/policies/policy-access-review-synthetic.md](bundle/policies/policy-access-review-synthetic.md) and [bundle/controls/control-quarterly-access-review-synthetic.md](bundle/controls/control-quarterly-access-review-synthetic.md).

## Field Mapping

| Source Field | OKF Location | Mapping Level | Notes |
| --- | --- | --- | --- |
| `id` | Concept file path `policies/policy-access-review-synthetic.md` and body section `# Source Object` | Partial mapping | OKF defines the concept ID as the path without `.md`. The path preserves the stable identifier, but OKF v0.1 does not define a standard `id` frontmatter field. |
| `object_type` | Frontmatter `type: Policy` and body section `# Source Object` | Partial mapping | OKF requires `type`, but type values are producer selected and not centrally registered. |
| `title` | Frontmatter `title` | Direct mapping | The value is copied from the source object. |
| `description` | Frontmatter `description` | Direct mapping | The value is copied from the source object. |
| `status` | Body section `# Lifecycle` | Partial mapping | OKF has no standard lifecycle state field. |
| `version` | Body section `# Lifecycle` | Partial mapping | OKF bundle versioning is not the same as policy object versioning. |
| `effective_date` | Body section `# Lifecycle` | Partial mapping | OKF has no standard effective date field. |
| `expiration_date` | Body section `# Lifecycle` | Partial mapping | OKF has no standard expiration date field. |
| `supersedes` | Body section `# Lifecycle` | Partial mapping | OKF links can express relationships in prose, but OKF v0.1 links are untyped edges. |
| `authoritative_source` | Body section `# Authority` | Partial mapping | OKF citations can point to sources, but OKF v0.1 does not define source authority semantics. |
| `source_uri` | Frontmatter `resource` and body section `# Authority` | Direct mapping | `resource` is the OKF field for the underlying asset URI. The worked example uses repository-relative URI references to inspectable source artifacts; production bundles could use authoritative absolute URIs. |
| `owner` | Body section `# Governance` | Partial mapping | OKF v0.1 has no standard owner field. |
| `steward` | Body section `# Governance` | Partial mapping | OKF v0.1 has no standard steward field. |
| `jurisdiction` | Body section `# Governance` | Partial mapping | OKF v0.1 has no standard jurisdiction field. |
| `applicability` | Body section `# Governance` | Partial mapping | OKF v0.1 can link concepts, but it does not define applicability semantics. |
| `classification` | Body section `# Permissions` | Partial mapping | OKF v0.1 does not enforce classification or usage controls. |
| `access_policy` | Body section `# Permissions` | Partial mapping | The policy details are visible in markdown, but OKF v0.1 does not define permission enforcement semantics. |
| `provenance` | Body section `# Provenance` | Partial mapping | OKF citations can cite sources, but OKF v0.1 does not define provenance fields. |
| `last_reviewed_date` | Body section `# Provenance` | Partial mapping | OKF `timestamp` expects an ISO 8601 datetime for last meaningful change. The source has a date, so the example does not invent a time. |
| `related_objects` | Body section `# Relationships` | Partial mapping | Markdown links can express relationships, but OKF v0.1 treats graph edges as untyped unless prose supplies context. |
| `related_objects.relationship_type` | Body section `# Relationships` | Partial mapping | Outgoing typed relationships can be represented as Markdown links and text. OKF v0.1 does not define standard fields for typed relationships. |
| Derived incoming relationship lookup | Body section `# Incoming Relationships` | Partial mapping | Incoming relationships can be calculated from the canonical relationship records and displayed as Markdown links. OKF v0.1 does not define standard fields for backlinks. This example does not claim formal OKF support for backlink semantics. |
| `assertions` | Body section `# Assertions` | Partial mapping | OKF v0.1 does not define an assertion model. |
| `evidence` | Body section `# Evidence` and `# Citations` | Partial mapping | OKF citations preserve evidence links, but evidence IDs and confidence semantics are not standard OKF fields. |
| `policy_category` | Body section `# Policy Content` | Partial mapping | OKF tags could classify concepts, but this example avoids custom category semantics in frontmatter. |
| `policy_statement` | Body section `# Policy Content` | Partial mapping | OKF stores the statement as markdown body content. |
| `obligations` | Body section `# Obligations` | Partial mapping | OKF v0.1 does not define obligation records. |
| `exception_process` | Body section `# Policy Content` | Partial mapping | OKF stores the process as markdown body content. |

## Unsupported Concepts

| Concept | Reason |
| --- | --- |
| Permission enforcement | OKF v0.1 stores markdown and frontmatter. It does not enforce access policy, denied uses, or handling notes. |
| Typed relationship semantics | OKF v0.1 treats links as directed edges whose exact relationship is conveyed by surrounding prose. |
| Backlink semantics | OKF v0.1 does not define a standard backlink field. The example derives incoming relationships from canonical relationship records and displays them as Markdown links for navigation. |
| Canonical JSON Schema validation | OKF v0.1 does not validate the repository's JSON schema constraints. |
| Object lifecycle semantics | OKF v0.1 bundle versioning does not replace policy version, effective date, expiration date, or supersession rules. |
| Provenance model equivalence | OKF v0.1 citations can cite sources, but they do not carry the repository's full provenance object. |
| Assertion model equivalence | OKF v0.1 does not define assertion IDs, predicates, objects, or confidence values. |

## Loss Summary

The OKF concept document keeps the policy readable and portable as markdown, but it weakens machine-readable semantics for permissions, provenance, versioning, relationships, assertions, and evidence. The example is conceptually aligned with OKF v0.1 and follows the minimal conformance rules, but it is not a verified lossless conversion.
