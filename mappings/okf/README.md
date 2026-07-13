# Open Knowledge Format Mapping

This directory contains a worked Open Knowledge Format example for the existing canonical JSON policy object at [../../examples/schema-examples/policy.example.json](../../examples/schema-examples/policy.example.json) and control object at [../../examples/schema-examples/control.example.json](../../examples/schema-examples/control.example.json). The source objects describe synthetic customer record system access review; this repository does not currently contain a separate canonical JSON customer data retention policy object.

The OKF example is a projection, not a replacement for the repository's canonical JSON representation. OKF is treated here as one example of the direction toward portable enterprise knowledge, not as this repository's canonical format or preferred target.

## Primary OKF Sources Checked

| Source Type | Source URL | Publication Date | Version |
| --- | --- | --- | --- |
| Official introduction and announcement | [GoogleCloudPlatform knowledge-catalog OKF README](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/README.md) | 2026-06-12 initial OKF commit date in the reference repository | Links to OKF v0.1 |
| Official specification | [Open Knowledge Format SPEC.md](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md) | 2026-06-12 initial OKF commit date in the reference repository | 0.1 Draft |
| Official schema | No separate schema was found. The OKF v0.1 specification states that there is no schema registry and defines conformance rules in the specification. | 2026-06-12 initial OKF commit date in the reference repository | 0.1 Draft |
| Official reference repository | [GoogleCloudPlatform/knowledge-catalog](https://github.com/GoogleCloudPlatform/knowledge-catalog) | Repository created 2026-05-04; OKF imported 2026-06-12 | OKF v0.1 Draft |

## Files

- [mapping-table.md](mapping-table.md) explains direct mappings, partial mappings, and unsupported concepts.
- [bundle/index.md](bundle/index.md) is the root index for the OKF v0.1 bundle.
- [bundle/policies/policy-access-review-synthetic.md](bundle/policies/policy-access-review-synthetic.md) is the OKF concept document derived from the canonical JSON source object.
- [bundle/controls/control-quarterly-access-review-synthetic.md](bundle/controls/control-quarterly-access-review-synthetic.md) is the OKF control concept document derived from the canonical JSON control source object.
- [bundle/sources/](bundle/sources/) contains fictional source and evidence artifacts that make the worked example self-contained and inspectable.

## Relationship And Backlink Example

The policy links to the control it requires. The control links to the policy it implements. The control also displays the policy as an incoming relationship.

The incoming relationship is derived from the canonical source records. OKF v0.1 supplies the Markdown bundle structure, but it does not define a standard backlink field or typed relationship model. The backlink display is a repository convention for making canonical relationships easier to navigate.

These policy/control links are relationships between knowledge objects. They are separate from provenance and evidence references, which point to supporting source artifacts in [bundle/sources/](bundle/sources/).

The source artifacts are fictional demonstration files included so readers can inspect the supporting material without following intentionally non-resolving placeholder URLs. A production bundle could instead point `resource`, `source_uri`, and evidence references at authoritative absolute URIs owned by the source system.

## Conformance Boundary

The bundle follows the OKF v0.1 Draft structure: markdown files with YAML frontmatter, a non-empty `type` field on the concept document, and a bundle root `index.md` declaring `okf_version: "0.1"`. The example does not claim lossless conversion from the repository's JSON model to OKF.

OKF permits producer-defined frontmatter keys, but this example avoids custom frontmatter so that it does not present repository-specific fields as OKF fields. Governance details that OKF v0.1 does not define as standard frontmatter are preserved in the markdown body instead.
