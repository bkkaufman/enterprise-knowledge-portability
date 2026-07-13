# Why Portability Matters

[Knowledge portability is the next AI architecture problem](https://articles.example.invalid/knowledge-portability-next-ai-architecture-problem) argues that enterprise knowledge needs a durable form outside any single model, index, workflow, or vendor system. This repository substantiates that thesis with synthetic records, schemas, relationships, and patterns rather than restating the article as prose.

## Retrieval Index Drift

Project retrieval indexes usually contain a copy of selected source material, not the governed knowledge object itself. Once copied, each index has its own chunking choices, embedding model, refresh cadence, filters, metadata fields, and deletion behavior. Two teams can start from the same policy and end up with different searchable fragments, different metadata loss, and different answers after one source changes. Drift is not only a sync problem; it is a loss of shared identity, authority, and lifecycle state across the places where AI systems look for context.

## Summaries Lose Authority

Summaries are useful reading aids, but they are weak containers for enterprise knowledge. A summary often collapses source, author, approval path, review date, exceptions, jurisdiction, and evidence into fluent text. That text may be easier to retrieve, but it no longer proves which source asserted the claim or whether the claim is still current. Portable records keep summaries beside authority, provenance, dates, and evidence instead of treating the summary as the record.

## Permissions Must Travel

Knowledge does not become safe to use just because it has been converted into text, chunks, triples, or embeddings. Permissions need to travel with the object because downstream systems may reuse the same knowledge in search, drafting, review, routing, and action execution. A record that is safe for validation may be unsafe for external publication or automated decision use. The access policy in the portable record gives adapters something explicit to preserve and enforce.

## Versions And Supersession

Enterprise knowledge changes through replacement, retirement, exception, and scope change. A current policy may supersede an older one, while historical evidence may still need to point to the policy version that applied on a prior date. Without version and supersession relationships, AI systems can mix old and current rules or erase the trail needed to explain why a decision was made. Portability requires identity over time, not only the latest text.

## Conflicting Sources

Conflicts are normal in enterprise knowledge: a policy, control library, system record, and local procedure may disagree. A retrieval pipeline that silently ranks one source over another hides the conflict inside a score. Portable knowledge should preserve conflicting records, mark their status, identify their sources, and provide a review path. The goal is not automatic resolution; it is explicit handling before the knowledge drives an answer or action.

## More Than File Format

Portability extends beyond file format. JSON, YAML, Markdown, RDF, and graph databases can all carry useful representations, but none of them guarantees stable identifiers, authority, permissions, provenance, supersession, conflict handling, or operational relationships. The architecture problem is deciding what must remain attached to knowledge when it moves between tools. File format is only the serialization layer.

Google's Open Knowledge Format is one recent signal that the market is moving toward portable knowledge representations. This repository does not depend on OKF, and it does not treat OKF as the only valid approach. The reference model here is deliberately small: common envelopes, policy and control schemas, relationship records, and patterns that can be adapted to other formats.

## From Retrieval To Execution

The problem becomes more acute when AI moves from retrieval into decision support and workflow execution. A retrieval answer can be reviewed by a person before use. A workflow step may route a case, request evidence, approve an exception, open a task, or trigger a downstream control check. At that point the system needs to know which knowledge object it used, whether it was current, whether it applied to the jurisdiction and capability in scope, whether the user was allowed to use it for that purpose, and whether any conflict existed. Portable knowledge gives the execution layer governed context instead of isolated text fragments.
