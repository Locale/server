# server

# Principles

- Standards based (BCP47, CLDR, etc...)
- Fully versioned audit trail.
- Small tool that does only one thing, but very well.

# Objectives

- [ ] Consolidate Translation Memory and Term Base with working translation content in the same format.
- [ ] Define patterns for multi-sentence segmentation.
- [ ] Support pluralization of strings.
- [ ] Define usage patterns for common translation workflows.
- [ ] Dissociate storage from the API interface.

# Schema

```graphql

type Language {
  id: ID!
}

type Organization {
  id: ID
  name: String
  projects: [Project]
}

type Project {
  sourceLanguage: Language!
  targetLanguages: [Languages]!
  documents: [Document]
}

type Document {
  segments: [Segment]
}

type Segment {
  key: String!
  units: [Unit]
}

type Unit {
  language: Language
}

```
