# server

# Principles

- Standards based (BCP47, CLDR, etc...).
- Opinionated, works in 80% of cases.
- Fully versioned audit trail.
- Small tool that does only one thing, but very well.
- File format AND API are the same thing.
- Flexible querying for advanced or unknown use cases.

# Objectives

- [ ] Consolidate Translation Memory and Term Base with working translation content in the same format.
- [ ] Define patterns for multi-sentence segmentation.
- [ ] Support pluralization of strings.
- [ ] Define usage patterns for common translation workflows.
- [ ] Dissociate storage from the API interface.
- [ ] Packageable, run anywhere, on any infrastructure.
- [ ] Automatic hashing of keys and content.

# Schema

```graphql

type Segment {
  key: String!
  units: [Unit]
}

type Unit {
  language: Language
}

```
