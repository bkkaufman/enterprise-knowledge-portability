# Design Principles

Portable enterprise knowledge should remain understandable outside the tool that first created it. The records in this repository are intentionally plain, explicit, and small enough to inspect without specialized infrastructure.

## Vendor Neutrality

Records do not assume a specific AI model, agent framework, cloud platform, vector database, graph database, workflow engine, or document system. A downstream implementation can adapt the records to those environments without changing the source knowledge.

## Synthetic Public Examples

Every identifier, organization, system, jurisdiction, and URL is synthetic. The examples are designed to show structure rather than encode real policy logic, production controls, or proprietary ontology concepts.

## Explicit Context

Knowledge records include source authority, provenance, permissions, jurisdiction, lifecycle status, effective dates, and supersession metadata so downstream systems can reason about fitness for use rather than treating every record as equally authoritative.

## Relationship First

Enterprise knowledge is useful when objects can be connected. The example separates objects from relationships so the same policy, control, system, or owner can participate in many contexts without duplicating the object.

## Small Surface Area

The first release uses a small set of schemas and one coherent domain. This keeps the architecture auditable and avoids turning the repository into a general framework before the portability pattern is clear.
