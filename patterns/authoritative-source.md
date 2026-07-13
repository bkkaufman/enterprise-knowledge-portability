# Authoritative Source

Portable knowledge records should identify the authority that asserts the record. The authority is separate from the system that stores or retrieves the record.

## Pattern

Each record includes `source_authority` with an identifier, authority type, and URL. The URL uses `example.invalid` in this public repository, but a private implementation could map the field to a policy portal, control library, system inventory, or governance register.

## Why It Matters

AI systems and workflow tools often combine records from many sources. Without source authority, downstream systems cannot distinguish an approved policy from a draft, a control owner's assertion from a system inventory export, or a conflicting record that needs review.

## Public Boundary

This repository shows only generic authority types and synthetic authority identifiers. It does not publish real committees, approval chains, control libraries, or internal governance sources.
