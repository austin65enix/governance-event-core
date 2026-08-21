# Extension Model

Profiles may define controlled vocabularies for:

- `event_type`
- `source_system`
- `source_event_type`
- `authority_stage`

Profiles may also add source locators, domain identifiers, execution identifiers, and domain authority flags.

A profile must not weaken source identity preservation, infer causality from timestamps alone, collapse governance meaning, convert negative authority into positive authority, or cause qualification itself to grant authority.

## Strict core with explicit extension container
The v0.1 core distinguishes **vocabulary extension** from **structural extension**. Open vocabularies extend values within defined core fields. Profile- or domain-specific structural data MUST be placed inside the optional `extensions` object. The top-level event object remains closed; profiles MUST NOT add arbitrary top-level fields. Profiles MUST NOT weaken source identity preservation, negative authority preservation, or the rule that qualification does not grant or advance authority.
