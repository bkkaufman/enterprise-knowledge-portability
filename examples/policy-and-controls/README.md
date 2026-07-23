# Policy And Controls Example

This example models synthetic enterprise policy and control knowledge for Synthetic Regulated Company, a fictional regulated organization.

The example shows how policies, controls, systems, owners, jurisdictions, capabilities, source authority, permissions, provenance, conflicts, and supersession can be represented as portable records. It does not depend on any AI vendor, workflow tool, retrieval system, graph database, vector database, or agent framework.

## Contents

- [knowledge-objects/policies.yaml](knowledge-objects/policies.yaml) contains synthetic policy records.
- [knowledge-objects/controls.yaml](knowledge-objects/controls.yaml) contains synthetic operational control records.
- [knowledge-objects/business-capabilities.yaml](knowledge-objects/business-capabilities.yaml) contains synthetic business capabilities.
- [knowledge-objects/systems.yaml](knowledge-objects/systems.yaml) contains synthetic systems.
- [knowledge-objects/owners.yaml](knowledge-objects/owners.yaml) contains synthetic accountable owners.
- [knowledge-objects/jurisdictions.yaml](knowledge-objects/jurisdictions.yaml) contains synthetic jurisdictions.
- [relationships/policy-control-relationships.yaml](relationships/policy-control-relationships.yaml) connects policies, controls, systems, owners, capabilities, and jurisdictions.
- [conflict-example/README.md](conflict-example/README.md) explains the conflict example.
- [conflict-example/conflicting-records.yaml](conflict-example/conflicting-records.yaml) contains two intentionally conflicting synthetic records.
- [supersession-example/README.md](supersession-example/README.md) explains the supersession example.
- [supersession-example/superseded-policies.yaml](supersession-example/superseded-policies.yaml) contains a synthetic policy version chain.
- [../document-authority-and-derivation/README.md](../document-authority-and-derivation/README.md) explains how the same access review policy domain distinguishes authoritative records from copies and derivatives.

## Portability Goal

The same source records can be loaded into many downstream systems because the durable knowledge is expressed before any platform-specific implementation choice is made.
