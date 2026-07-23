# Document Authority And Derivation

Portable knowledge records should distinguish the approved knowledge object from documents that represent, copy, summarize, translate, attach, or generate from it.

## Pattern

A knowledge object carries the governed statement: policy, control, owner, system, jurisdiction, or another approved enterprise record. A document artifact carries a representation or derivative of that object: a PDF export, collaboration repository copy, generated summary, translation, attachment, or operating procedure.

The storage location is metadata about where an object or artifact resides. A policy management system, collaboration repository, AI summarization service, workflow system, or file share can hold content, but storage does not by itself establish authority.

Authority comes from scoped governance metadata: source authority, lifecycle status, applicability, jurisdiction, effective period, supersession, permitted uses, and artifact verification.

## Exact Copies And Derivatives

An exact copy preserves the same bytes as another artifact. A matching SHA-256 fingerprint can verify byte identity for the content that was hashed.

A transformed derivative changes form or meaning risk. Summaries, translations, generated procedures, excerpts, and rewritten pages may be useful for reading or navigation, but they need their own approval rules before they can control policy interpretation, control requirements, or operational execution.

Different hashes do not prove that two documents have different meaning. A file can be re-rendered, re-encoded, or packaged differently while preserving the same business meaning. Semantic similarity can identify possible copies or derivatives, but neither similarity nor retrieval rank establishes authority.

## Artifact Lineage

Lineage relationships connect artifacts and knowledge objects with explicit direction:

- `represents`: an artifact represents a knowledge object.
- `exported_from`: an artifact was exported from a knowledge object or source record.
- `exact_copy_of`: an artifact has verified byte identity with another artifact.
- `derived_from`: an artifact was created from another artifact or knowledge object through transformation.
- `summarizes`: an artifact summarizes another artifact or knowledge object.
- `translated_from`: an artifact is a translation of another artifact or knowledge object.

These relationships complement existing relationships such as `supersedes`, `conflicts_with`, and `references`. They do not replace source authority or lifecycle metadata.

## Scoped Authority

Authority is scoped. The same file can be fit for one use and unfit for another.

A controlled export may be usable for policy interpretation on an effective date. A verified copy may be usable to prove that a collaboration repository file matches the export. An AI generated summary may be usable for orientation but prohibited for policy interpretation. A generated procedure may be useful as a draft but unable to govern operational steps until an approved authority accepts it.

Scoped authority should account for:

- Knowledge domain.
- Decision type.
- Jurisdiction or applicability.
- Effective date or effective period.
- Lifecycle status.
- Source authority.
- Controlling knowledge object.
- Controlling artifact, if one applies.
- Permitted and prohibited uses.
- Artifact lineage and verification.

## Retrieved Does Not Mean Authoritative

Retrieval systems optimize for matching a query, not for governance. A retrieved document may be stale, copied, summarized, translated, generated, or stored in a system that has no approval authority.

Downstream AI and workflow systems should treat retrieved artifacts as candidates. They should resolve authority through metadata and relationships before using a candidate for a governed decision.

## Conflicts

If candidate records conflict and the conflict is unresolved, downstream systems should not choose the most recent, most detailed, or most retrieved artifact by default. They should block, escalate, or return a conflict result that names the records, authorities, scope, and missing resolution.

## Public Boundary

This pattern is synthetic. It does not define a production policy engine, legal interpretation process, document management workflow, or approval chain. It shows where authority and derivation metadata can be preserved so downstream systems can evaluate candidates against governed rules.
