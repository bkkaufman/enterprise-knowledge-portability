# Schema Design Notes

The schemas use JSON Schema Draft 2020-12 and keep the common portable record envelope in [knowledge-object.schema.json](knowledge-object.schema.json). Policy, control, and relationship schemas compose that envelope with `allOf` and add only the fields needed for the object type.

## Common Envelope

Every knowledge object can carry stable identity, object type, title, description, status, version, dates, supersession, source authority, ownership, stewardship, jurisdiction, applicability, classification, access policy, provenance, review date, related objects, machine-readable assertions, and human-readable evidence.

The common schema intentionally uses plain strings, arrays, and small objects. It validates record shape, controlled values, dates, public example URI references, and synthetic identifier format. It does not define enterprise semantics, legal meaning, control effectiveness, ontology reasoning, or downstream runtime behavior.

## Composition

[policy.schema.json](policy.schema.json) adds policy category, policy statement, obligations, and exception process. [control.schema.json](control.schema.json) adds control category, objective, type, frequency, systems, obligation mappings, and evidence expectations. [relationship.schema.json](relationship.schema.json) composes the same envelope so relationships can carry authority, provenance, access policy, and review metadata. [document-artifact.schema.json](document-artifact.schema.json) is a sibling schema for files, exports, copies, summaries, translations, attachments, and generated documents that represent or derive from knowledge objects.

## Public Example Boundary

The schemas require synthetic identifiers ending in `-synthetic` and source or evidence URI references that are either repository-relative artifacts or HTTPS `example.invalid` placeholders. This keeps the public reference examples clearly synthetic while allowing the primary OKF worked example to point at inspectable files in the repository. A private implementation would normally relax those patterns and map identifiers to its own governed namespace or authoritative source-system URLs.

## Examples

Valid JSON examples are in [../examples/schema-examples](../examples/schema-examples):

- [knowledge-object.example.json](../examples/schema-examples/knowledge-object.example.json)
- [policy.example.json](../examples/schema-examples/policy.example.json)
- [control.example.json](../examples/schema-examples/control.example.json)
- [relationship.example.json](../examples/schema-examples/relationship.example.json)

Document artifact examples are in [../examples/document-authority-and-derivation/artifacts](../examples/document-authority-and-derivation/artifacts).

## Tradeoffs

- The envelope requires the main governance fields so examples cannot omit authority, access policy, provenance, or evidence.
- `expiration_date` allows `null` because many active records do not have a known retirement date.
- Assertions use a compact predicate and object form. This is useful for validation and exchange, but it is not a substitute for a domain ontology or rule engine.
- Access policy is descriptive metadata. It does not enforce access control by itself.
- Relationship records are first-class objects in this reference so they can be reviewed, versioned, and traced like policies and controls.
- Document artifacts do not compose the full common envelope because many artifacts are copies or derivatives rather than governed knowledge objects. The artifact schema reuses common identifier, URI, and relationship definitions where those fields apply.
