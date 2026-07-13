# Reference JSON Representation

This repository treats JSON knowledge objects as the reference representation for its public examples. That means the JSON files define the record shape used by the schemas, examples, and mapping notes in this repository. It does not mean this JSON model is a universal standard or the only valid way to represent portable knowledge.

The policy example at [../examples/schema-examples/policy.example.json](../examples/schema-examples/policy.example.json) is the source object used by the projection notes. It carries the fields that matter for portability: stable identifier, object type, title, description, lifecycle state, version, effective dates, source, owner, steward, jurisdiction, applicability, classification, access policy, provenance, review date, related objects, assertions, evidence, policy statement, obligations, and exception process.

## Why JSON Is The Reference Here

JSON is useful in this repository because it can be validated against JSON Schema Draft 2020-12, preserves object keys predictably, and can be read by common tooling. The schemas can require governance fields and constrain values such as status, classification, dates, and synthetic identifiers.

The JSON representation is still only a repository choice. It does not prove semantic correctness, enforce permissions, resolve conflicts, or guarantee that downstream tools will preserve every field. Those outcomes require governance, review, adapters, and tests.

## Preservation Profile

| Aspect | Status In Reference JSON |
| --- | --- |
| Stable identity | Direct mapping through `id`. |
| Authority and source | Direct mapping through `authoritative_source` and `source_uri`. |
| Provenance | Direct mapping through the `provenance` object. |
| Permissions | Direct mapping through `classification` and `access_policy`. |
| Versioning | Direct mapping through `version`, `effective_date`, `expiration_date`, and `supersedes`. |
| Relationships | Direct mapping through `related_objects`; separate relationship records can add more context. |
| Assertions and evidence | Direct mapping through `assertions` and `evidence`. |
| Human readability | Partial mapping because JSON is readable, but not ideal for policy readers. |

## Projection Rule

Other formats should be treated as projections from the reference object. A projection may optimize for editing, publication, review, or exchange, but it should state what it preserves, weakens, or loses. This release does not include conversion software.
