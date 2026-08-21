# Governance Event Core v0.1

Governance Event Core defines an implementation-neutral surface for representing and semantically qualifying governance events.

## Normative artifacts

- `schemas/canonical-governance-event-core-v0.1.schema.json`
- `contracts/governance-event-mapping-v0.1.json`
- `contracts/governance-semantic-qualification-v0.1.json`

## Core principles

- preserve source event identity;
- preserve source event type;
- do not infer causality from timestamps alone;
- do not collapse authority stages;
- preserve negative authority information;
- prefer absent lineage to invented lineage;
- qualification does not grant authority.

## Conformance

See `docs/conformance-model.md` and `conformance/`.

## Extensions

Domain profiles may define vocabularies and additional fields while preserving the core invariants.

## Non-claims

Version 0.1 does not define governed-run identity, an authorization state machine, durable closeout, runtime execution, persistence, database bindings, or product-specific source profiles.

## Extension boundary
The core schema keeps the top-level event object closed (`additionalProperties: false`). Open vocabularies extend values inside defined core fields; they do not permit arbitrary top-level fields. Profile- or domain-specific structural data belongs under the optional `extensions` object. Unknown top-level fields remain invalid.

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE).
