# Authority Resolution

Authority resolution answers a scoped governance question: which record or artifact controls a particular decision on a particular date?

It is not a confidence score, retrieval ranking, semantic similarity result, or model judgment. It is a governed selection based on explicit metadata and rules defined by the organization.

## Pattern

Use a transparent sequence that keeps candidates visible and explains exclusions:

1. Identify the requested knowledge domain and decision type.
2. Filter by applicability and jurisdiction.
3. Filter by effective date and lifecycle status.
4. Identify the authority permitted to assert the record.
5. Resolve supersession.
6. Evaluate artifact lineage and verification.
7. Enforce permissions and permitted uses.
8. Block or escalate when unresolved conflicts remain.
9. Return the selected record and explain excluded alternatives.

## Sequence

Start with the decision request. The request should state the domain, decision type, requested use, date, jurisdiction, and applicability. A request for access review policy interpretation on 2026-07-01 is different from a request for historical audit context in 2025.

Filter candidates by scope before looking at storage location. A file in a collaboration repository may match the query, but it is only a candidate until its represented object, lifecycle status, effective period, permissions, and lineage are evaluated.

Check that the asserting authority is allowed to approve or assert that knowledge for the requested scope. A control owner may assert control operation metadata. A policy standards board may approve policy requirements. A summarization service can create a summary, but it cannot become the policy authority by storing a generated file.

Resolve supersession before choosing among artifacts. If a current policy supersedes an older version, copies of the older version should be excluded for current decisions unless the request is explicitly historical and falls inside the older effective period.

Evaluate lineage after the controlling knowledge object is known. An approved export may be a controlled representation. A verified copy may prove byte identity with that export. A summary or generated procedure may be a derivative that needs separate approval before it can control a decision.

Enforce permitted and prohibited uses last, because an otherwise valid record can still be unfit for a requested use. A summary may allow architecture reference but prohibit policy interpretation. A generated procedure may be pending approval and prohibited for operational execution.

## Output

The output should name:

- The controlling knowledge object.
- The controlling artifact or canonical location, if one applies.
- The asserting authority.
- The authority scope.
- The resolution date.
- The reasons the selected record was chosen.
- Each excluded candidate and the reason it was excluded.

The output should not hide discarded records. Exclusions are part of the audit trail.

## Conflicts

If two active records both appear to apply and neither supersedes the other, the resolver should return a conflict result rather than pick one by rank or recency. The conflict result should preserve the competing records, authorities, dates, and relationship metadata needed for human review.

## Public Boundary

This pattern is conceptual. The repository does not include a production policy engine, conflict adjudication workflow, graph database, vector index, or agent framework. It shows the metadata needed for downstream systems to make governed selection explainable.
