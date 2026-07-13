# Portability Model

The repository models enterprise knowledge as records that can be read by humans, validated by machines, and adapted into many application environments.

## Layer 1: Knowledge Object Envelope

Every record uses a common envelope with stable identity, type, title, summary, lifecycle status, effective dates, source authority, permissions, and provenance. This common envelope allows different object types to move through the same governance and integration processes.

## Layer 2: Domain-Specific Attributes

Policy and control records add fields that are specific enough to be useful but generic enough to remain public. For example, a policy can name jurisdictions and obligations, while a control can name control objectives, operating frequency, evidence expectations, and responsible owners.

## Layer 3: Relationships

Relationships are first-class records. A policy can require a control, a control can operate within a system, an owner can be accountable for a control, and a policy can supersede another policy version.

## Layer 4: Interpretation Patterns

Patterns explain how systems should interpret authority, provenance, permissions, versioning, and conflicts. These patterns are documented separately from the examples so they can be reused with other domains.

## Layer 5: Implementation Adapters

Adapters to AI vendors, retrieval systems, workflow tools, databases, and agent frameworks are intentionally excluded from this first release. The portable source records should remain independent of those downstream choices.

