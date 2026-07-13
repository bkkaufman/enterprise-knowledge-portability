# Permissions

Portable knowledge should carry usage permissions with the record instead of assuming every downstream system may use every record in every context.

## Pattern

Each record includes `permissions` with a classification, allowed uses, and denied uses. The first release uses public example classifications only.

## Why It Matters

AI and automation systems can separate knowledge that is safe for demonstration, retrieval, summarization, workflow execution, or compliance attestation. The permissions field helps downstream systems enforce use constraints without binding the source records to one vendor's access model.

## Public Boundary

This repository does not define real access control, entitlements, user groups, or enforcement logic. It only demonstrates how permission metadata can travel with portable knowledge records.

