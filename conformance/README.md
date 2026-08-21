# Conformance Fixtures

The fixture set demonstrates the v0.1 canonical event schema boundary.

Planned valid fixtures:

- `fixtures/valid/minimum-core-event.json`
- `fixtures/valid/open-vocabulary-event.json`

Planned invalid fixtures:

- `fixtures/invalid/missing-event-id.json`
- `fixtures/invalid/wrong-sequence-number-type.json`

These fixtures do not prove execution authorization, state-transition validity, durable closeout, runtime behavior, or persistence behavior.

## Extension boundary fixtures
- `fixtures/valid/extension-container-event.json` — expected **VALID**.
- `fixtures/invalid/unknown-top-level-field.json` — expected **INVALID_SCHEMA** because arbitrary top-level fields are rejected.
