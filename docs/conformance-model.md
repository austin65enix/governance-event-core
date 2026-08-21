# Conformance Model

Governance Event Core v0.1 defines nine initial assertions:

- C01 JSON artifacts are syntactically valid.
- C02 Required core fields are present.
- C03 Core vocabularies remain open.
- C04 Profile-only fields are outside the minimum core.
- C05 Mapping invariants are present.
- C06 Product-specific mapping instances are absent.
- C07 Qualification does not promote authority.
- C08 Shared mapping and qualification invariants remain aligned.
- C09 Public artifacts contain no internal implementation dependency.

Fixtures are classified as `VALID` or `INVALID_SCHEMA`.

## Extension boundary assertions
- **C10 — Explicit extension container accepted:** an otherwise valid event remains valid when profile- or domain-specific data is placed inside `extensions`.
- **C11 — Unknown top-level field rejected:** an otherwise valid event becomes schema-invalid when an undeclared top-level field is added outside `extensions`.
