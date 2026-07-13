# Enterprise Knowledge Portability

Enterprise knowledge should remain understandable, authoritative, and reusable when models, vendors, applications, and workflows change.

This repository is a public reference implementation for structuring enterprise knowledge outside any single AI model, application database, retrieval index, workflow engine, or vendor-specific agent memory system.

The repository also includes an [Open Knowledge Format example](mappings/okf/README.md), showing how the same portable policy record can be represented as an OKF v0.1 Draft bundle without making OKF the canonical source model.

## The Enterprise Problem

Enterprises often encode important operating knowledge in places that are hard to move: policy portals, control libraries, ticket workflows, application tables, knowledge bases, retrieval indexes, prompts, and agent memory stores. When the organization changes models, vendors, applications, or workflows, that knowledge can lose context, authority, provenance, permissions, effective dates, and relationships to the controls or systems that make it operational.

This migration cost often comes with a deeper operational problem: teams can no longer tell which records are authoritative, which version applies, what a record depends on, who owns it, what evidence supports it, or whether a downstream AI or automation system is allowed to use it.

## What Portability Means Here

Portability means enterprise knowledge is represented in a way that can be inspected, validated, governed, and adapted before it is loaded into a model, index, graph, workflow tool, or agent runtime.

In this repository, portable knowledge has:

- Stable identifiers.
- Explicit object types.
- Human-readable summaries.
- Source authority.
- Provenance.
- Permissions.
- Effective dates.
- Supersession metadata.
- Relationships to other knowledge objects.
- Conflict records instead of silent overwrites.

## What This Repository Demonstrates

The first release demonstrates a small synthetic domain: enterprise policy and control management for a fictional regulated company.

It includes portable records for policies, controls, business capabilities, systems, owners, jurisdictions, effective dates, superseded versions, source authority, permissions, provenance, conflicting records, and relationships between policies and operational controls.

The repository does not implement an ontology, RDF model, OWL model, SHACL validation layer, graph database, vector database, retrieval pipeline, or agent framework. Those may be downstream implementation choices, but they are not the source representation.

## Overview

```mermaid
flowchart TD
  A[Portable knowledge objects] --> B[Policies]
  A --> C[Controls]
  A --> D[Business capabilities]
  A --> E[Systems]
  A --> F[Owners and jurisdictions]
  B --> G[Relationship records]
  C --> G
  D --> G
  E --> G
  F --> G
  G --> H[Authority, provenance, permissions, versions, conflicts]
  H --> I[Downstream adapters]
  I --> J[AI models]
  I --> K[Retrieval systems]
  I --> L[Workflow tools]
  I --> M[Agent runtimes]
```

## Repository Map

| Area | Link | Purpose |
| --- | --- | --- |
| Scope | [docs/scope.md](docs/scope.md) | Defines what this public reference includes and excludes. |
| Why portability matters | [docs/why-portability-matters.md](docs/why-portability-matters.md) | Explains the architecture problem behind portable enterprise knowledge. |
| Design principles | [docs/design-principles.md](docs/design-principles.md) | Explains the modeling principles behind the examples. |
| Portability model | [docs/portability-model.md](docs/portability-model.md) | Describes the layers used to keep knowledge independent of downstream tools. |
| Knowledge object schema | [schemas/knowledge-object.schema.json](schemas/knowledge-object.schema.json) | Defines the shared envelope for portable records. |
| Policy schema | [schemas/policy.schema.json](schemas/policy.schema.json) | Defines portable policy records. |
| Control schema | [schemas/control.schema.json](schemas/control.schema.json) | Defines portable operational control records. |
| Relationship schema | [schemas/relationship.schema.json](schemas/relationship.schema.json) | Defines relationships between portable records. |
| Format mappings | [mappings/canonical-json.md](mappings/canonical-json.md) | Shows how the reference JSON objects can be projected into other formats. |
| Worked example | [examples/policy-and-controls/README.md](examples/policy-and-controls/README.md) | Shows the synthetic policy and control management domain. |
| Authoritative source pattern | [patterns/authoritative-source.md](patterns/authoritative-source.md) | Describes how records identify the authority that asserts them. |
| Provenance pattern | [patterns/provenance.md](patterns/provenance.md) | Describes how records carry origin and review metadata. |
| Versioning pattern | [patterns/versioning-and-supersession.md](patterns/versioning-and-supersession.md) | Describes how records preserve effective dates and supersession history. |
| Permissions pattern | [patterns/permissions.md](patterns/permissions.md) | Describes how records carry usage constraints. |
| Conflict resolution pattern | [patterns/conflict-resolution.md](patterns/conflict-resolution.md) | Describes how conflicting records are preserved and marked. |

## Starting Point

Start with [docs/portability-model.md](docs/portability-model.md), then read the worked example at [examples/policy-and-controls/README.md](examples/policy-and-controls/README.md). After that, inspect [schemas/knowledge-object.schema.json](schemas/knowledge-object.schema.json) to see the common record envelope used across the example.

## Intended Audience

This repository is intended for enterprise architects, AI platform teams, knowledge management teams, governance teams, and engineers who need enterprise knowledge to remain usable across changing AI and application environments.

It is also intended for reviewers who need to understand where authority, permissions, provenance, versioning, and conflict handling are represented before knowledge is used by AI systems or automated workflows.

## Scope And Limitations

This repository provides public reference patterns and synthetic example files. It is not a compliance framework, legal interpretation, policy authoring system, access control implementation, data catalog, model memory service, or production control library.

The examples are intentionally small. They are designed to show structure and boundaries, not to model a complete regulated enterprise or a complete control environment.

## Relationship To Existing Formats And Systems

Formats such as OKF, Markdown, YAML, JSON, knowledge graphs, and vendor-specific agent memory can all be useful in different contexts. This repository treats them as possible representations, targets, or implementation environments rather than as the definition of the knowledge itself.

Markdown is useful for human-readable explanation. YAML and JSON are useful for portable structured records. Knowledge graphs can represent relationships and traversal. Vendor-specific agent memory can support runtime behavior. OKF and similar formats can influence how structured knowledge is exchanged. None of these should be the only place where enterprise meaning, authority, permissions, provenance, and version history exist.

The pattern in this repository is to define canonical knowledge records first, then adapt them to the format or runtime needed for a specific implementation.

## Relationship To Second Brain And Wiki-Style Knowledge Systems

This repository shares some of the thinking behind Andrej Karpathy’s second brain work and concepts. Knowledge is more usable when it is maintained as readable, linked pages that people and software can navigate through.

The same approach is useful inside an enterprise. Policies, controls, systems, owners, evidence, and decisions can each have a persistent page, with links showing how they relate to one another. This gives people and AI systems a clearer structure than a collection of document fragments stored in separate retrieval indexes.

Enterprise knowledge also needs information that a personal knowledge system may not require. Each record may need an authoritative source, ownership, permissions, effective dates, provenance, and a defined lifecycle. Relationships also need clear meaning. A policy may require a control, a control may implement a policy, and a newer record may supersede an earlier one.

**Backlinks** make these relationships visible from both directions. A policy page can point to the control required, while the control page can show every policy that depends on it. In this repository, the backlink is derived from the canonical `related_objects` entries in the source records and displayed in the Markdown projection.

## Open Knowledge Format Example

This repository includes a concrete **Open Knowledge Format** implementation.

The example projects the existing canonical JSON policy and control records into an OKF v0.1 Draft bundle. The bundle contains an `index.md` file and Markdown knowledge concepts with YAML frontmatter.

A minimal OKF concept in this repository looks like this:

```yaml
---
type: Policy
title: Synthetic Access Review Policy
description: A synthetic policy requiring periodic review of access to example business systems.
resource: ../sources/access-review-policy-source.md
---
```

The remaining authority, lifecycle, permissions, provenance, relationships, assertions, evidence, and obligations appear in the Markdown body. OKF v0.1 does not define standard frontmatter fields for all of those concepts.

The OKF worked example is self-contained: provenance and evidence references point to fictional source artifacts in the repository, while policy/control relationships use repository-relative Markdown links between OKF concepts. Production bundles could use authoritative absolute URIs instead.

Explore the example:

- [OKF mapping overview](mappings/okf/README.md)
- [OKF bundle index](mappings/okf/bundle/index.md)
- [OKF policy concept](mappings/okf/bundle/policies/policy-access-review-synthetic.md)
- [OKF control concept](mappings/okf/bundle/controls/control-quarterly-access-review-synthetic.md)
- [Field mapping table](mappings/okf/mapping-table.md)
- [Canonical JSON source object](examples/schema-examples/policy.example.json)
- [Canonical JSON control source object](examples/schema-examples/control.example.json)

The bundle also shows a relationship in both directions: the policy links to the control it requires, and the [control displays the policy as an incoming relationship](mappings/okf/bundle/controls/control-quarterly-access-review-synthetic.md#incoming-relationships).

The OKF representation is a projection of the canonical knowledge objects. It demonstrates how OKF can carry portable knowledge while also making clear which governance semantics map directly, which map partially, and which remain outside the current OKF specification.

## Vendor Neutral And Synthetic

This repository is vendor neutral. It does not depend on any AI provider, model provider, cloud provider, application vendor, vector database, graph database, workflow system, or agent framework.

All examples are synthetic. The fictional company, records, identifiers, systems, authorities, jurisdictions, source artifacts, and URLs are public examples only. The examples are not production systems and do not represent a real organization.

## Enterprise AI Architecture Notes

- [Enterprise AI Architecture Notes](https://notes.example.invalid/enterprise-ai-architecture) provides companion architecture notes for related enterprise AI design topics.

## License

Copyright © 2026 Brad Kaufman. All rights reserved.
