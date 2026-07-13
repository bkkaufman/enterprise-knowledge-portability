# Provenance

Provenance records how a knowledge object came to exist and when it was last reviewed. It is not the same thing as authority: authority says who can assert the record, while provenance says where the record came from and how it has been handled.

## Pattern

Each record includes `provenance` with a synthetic creator, creation date, last reviewed date, derivation type, and optional source record URL.

## Why It Matters

Portable knowledge will move across retrieval indexes, AI tools, workflow systems, and reporting environments. Provenance helps downstream systems evaluate freshness, traceability, and whether a record is synthetic, transformed, or imported.

## Public Boundary

The examples use synthetic creator names and `example.invalid` URLs. A public reference should not include real usernames, repository names, internal paths, ticket IDs, or production source locations.

