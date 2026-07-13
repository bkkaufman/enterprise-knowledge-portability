# OKF Alignment Notes

This note compares the repository's concepts with the public direction represented by Google's Open Knowledge Format. The worked example at [okf/README.md](okf/README.md) maps canonical JSON policy and control objects into an OKF v0.1 Draft bundle while keeping the canonical JSON model as the source of truth.

## Comparison Levels

| Level | Meaning |
| --- | --- |
| Direct mapping | The repository has an explicit field or record pattern for the concept. |
| Partial mapping | The repository can represent part of the concept, but extra rules or adapters would be needed. |
| Conceptual similarity | The repository's design intent appears aligned with the direction, but no field-level mapping is asserted. |
| Unsupported concept | OKF v0.1 does not define a standard representation for the concept. |

## Concept Comparison

| Repository Concept | Alignment Level | Notes |
| --- | --- | --- |
| Title and description | Direct mapping | OKF v0.1 defines `title` and `description` frontmatter fields. The worked example copies these values from the canonical JSON source object. |
| Source URI reference | Direct mapping | OKF v0.1 defines `resource` as the URI for the underlying asset. The worked example maps `source_uri` to `resource` and uses repository-relative source artifacts so the example is inspectable. |
| Stable knowledge object identity | Partial mapping | OKF v0.1 defines the concept ID as the markdown file path without `.md`. The worked example uses the source ID in the concept path and body, but OKF v0.1 does not define a standard `id` frontmatter field. |
| Object type | Partial mapping | OKF v0.1 requires `type`, but type values are producer selected and not centrally registered. |
| Authority and source | Partial mapping | OKF citations can cite sources, but OKF v0.1 does not define source authority semantics. |
| Provenance | Partial mapping | The worked example preserves provenance in markdown body content. OKF v0.1 does not define provenance frontmatter fields. |
| Permissions and classification | Partial mapping | The worked example preserves classification and access policy in markdown body content. OKF v0.1 does not enforce permissions. |
| Versioning and supersession | Partial mapping | The worked example preserves source version, effective date, expiration date, and supersession in markdown body content. OKF bundle versioning is separate from object lifecycle semantics. |
| Relationships between objects | Partial mapping | OKF links can create directed edges, but the relationship type is conveyed by prose rather than a standard field. |
| Machine-readable assertions | Unsupported concept | OKF v0.1 does not define assertion IDs, predicates, objects, or confidence values. The worked example keeps them in a markdown table. |
| Evidence IDs and evidence semantics | Partial mapping | OKF citations can link to evidence, but evidence IDs and confidence semantics are not standard OKF fields. |
| JSON reference representation | Conceptual similarity | The repository uses JSON as its local reference representation. OKF v0.1 uses markdown files with YAML frontmatter. |
| YAML and Markdown projections | Conceptual similarity | These projections demonstrate portability choices in this repository. The concrete OKF example is the only OKF projection in this release. |

## What This Repository Can Safely Claim

The repository can say that its design direction is compatible with the general need for portable, structured knowledge that preserves semantics, authority, provenance, permissions, versioning, and relationships across tools. That is conceptual alignment, not a claim that OKF is the only or preferred solution.

The repository can also say that the worked example follows OKF v0.1 Draft's minimal conformance rules: markdown concept documents with YAML frontmatter, a non-empty `type` field, and a bundle root `index.md` declaring `okf_version: "0.1"`.

The repository cannot claim lossless conversion to OKF, permission enforcement by OKF, equivalent provenance semantics, equivalent version lifecycle semantics, or typed relationship preservation.

## Release Boundary

This release does not build conversion software, validators for OKF, or adapters to vendor systems. The mapping notes are documentation only. They make projection tradeoffs explicit before any future implementation work begins.
