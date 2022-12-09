# server

A content server for handling localization


# Principles

- Standards based (BCP47, CLDR, etc...).
- Opinionated, works in 80% of cases. Convention over configuration.
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
- [ ] Capable of handling markup within content (eg. HTML).
- [ ] Handle placeholders/variables.
- [ ] Handle data types.

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
