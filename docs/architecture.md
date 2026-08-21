# Core Architecture

```text
Source Event
    |
    v
Authorized Mapping
    |
    v
Canonical Governance Event
    |
    v
Semantic Qualification
```

The core requires an authorized mapping but does not define how mapping authority is granted.

Canonicalization preserves source identity and governance meaning.

Semantic qualification evaluates the canonical representation. It does not grant authority or advance an authority stage.

Timestamp ordering alone is not proof of causality, and negative authority information must remain negative through mapping and qualification.
