# OKF Alignment Notes

This note compares the repository's concepts with the public direction represented by Google's Open Knowledge Format. It does not claim exact compatibility. This release has not verified a public field-level OKF specification, so it does not invent OKF fields or provide conversion software.

## Comparison Levels

| Level | Meaning |
| --- | --- |
| Direct mapping | The repository has an explicit field or record pattern for the concept. |
| Partial mapping | The repository can represent part of the concept, but extra rules or adapters would be needed. |
| Conceptual similarity | The repository's design intent appears aligned with the direction, but no field-level mapping is asserted. |
| Not verified | This release has no verified public OKF detail for the concept. |

## Concept Comparison

| Repository Concept | Alignment Level | Notes |
| --- | --- | --- |
| Stable knowledge object identity | Conceptual similarity | The repository uses stable synthetic IDs so objects can move between formats and tools. No OKF identifier field is asserted here. |
| Object type | Conceptual similarity | The repository separates policies, controls, relationships, systems, owners, capabilities, and jurisdictions. No OKF type field is asserted here. |
| Authority and source | Conceptual similarity | The repository treats authority as part of the portable object. Field-level OKF support is not verified in this release. |
| Provenance | Conceptual similarity | The repository carries creation method, author identity, date, and change summary. Exact OKF provenance handling is not verified. |
| Permissions and classification | Conceptual similarity | The repository keeps access policy and classification beside the object. OKF permission semantics are not verified. |
| Versioning and supersession | Conceptual similarity | The repository models version, effective dates, expiration, and supersedes relationships. Exact OKF lifecycle semantics are not verified. |
| Relationships between objects | Conceptual similarity | The repository has inline related objects and separate relationship records. Exact OKF relationship representation is not verified. |
| Machine-readable assertions | Conceptual similarity | The repository includes simple predicate and object assertions. No OKF assertion model is asserted here. |
| Human-readable evidence | Conceptual similarity | The repository links evidence summaries and URIs to the object. Exact OKF evidence handling is not verified. |
| JSON reference representation | Not verified | The repository uses JSON as its local reference representation. It does not claim JSON compatibility with OKF. |
| YAML and Markdown projections | Not verified | These projections demonstrate portability choices in this repository. They are not OKF projections. |

## What This Repository Can Safely Claim

The repository can say that its design direction is compatible with the general need for portable, structured knowledge that preserves semantics, authority, provenance, permissions, versioning, and relationships across tools. That is a conceptual similarity, not an exact mapping.

The repository cannot claim field-level OKF compatibility, lossless conversion to OKF, or conformance with an OKF specification unless a public specification is reviewed and mapped in a later release.

## Release Boundary

This release does not build conversion software, validators for OKF, or adapters to vendor systems. The mapping notes are documentation only. They are intended to make projection tradeoffs explicit before any future implementation work begins.
