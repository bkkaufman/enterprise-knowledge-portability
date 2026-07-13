# Scope

This repository demonstrates public, vendor-neutral patterns for making enterprise knowledge portable across AI models, agents, retrieval systems, workflow tools, and application runtimes.

The first release focuses on a single synthetic domain: enterprise policy and control management for a fictional regulated company. The example includes policies, operational controls, business capabilities, systems, owners, jurisdictions, effective dates, superseded versions, source authority, permissions, provenance, conflicting records, and relationships between policies and controls.

## In Scope

- Generic knowledge object structures that can be serialized as files.
- JSON Schema definitions for portable public examples.
- Synthetic policy and control records.
- Relationship records that connect policies, controls, systems, owners, capabilities, and jurisdictions.
- Public architecture patterns for authoritative source, provenance, versioning, permissions, and conflict resolution.
- Documentation that explains how to keep knowledge independent of vendor-specific AI or application systems.

## Out Of Scope

- Real company data, private schemas, internal URLs, client names, proprietary ontologies, confidential workflows, credentials, secrets, and production records.
- Ontology implementation files, RDF, OWL, SHACL, graph database setup, vector database setup, retrieval pipeline code, model prompts, agent framework adapters, cloud provider templates, and application integration code.
- Claims that the synthetic examples are complete regulatory controls or production-ready compliance artifacts.

## Public Boundary

The repository publishes shapes, examples, and patterns that are safe to discuss publicly. A private implementation may map these patterns to internal systems, private vocabularies, production workflows, and organization-specific governance processes, but those mappings do not belong in this public repository.

