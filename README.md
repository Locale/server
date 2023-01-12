# Blueberry :blueberries:

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

# Roadmap

## 0.0.1

- [ ] Basic structure, including Groups, Segments, Units.
- [ ] Ability to fetch data via GraphQL.

## 0.0.2

- [ ] Create items mutation.

## 0.0.3

- [ ] Pluralization.

# Schema

```graphql

version: 0.01

type Unit {
  id: String! # auto
  key: String!
  locale: String # future, extract to Class
  resource: String # optional, extract to Class
  text: String # raw text
  segments: [Segment] # auto
}

type Segment {
  type: String # text|numeric|html|plural|untranslatable
  value: String
}

```

### Quick XLIFF refresher

```
- File
  # the container for localization material extracted from the document
  
  |-- Group (optional)
  # a way to organize units into a structured hierarchy
  
      |-- Unit
      # a container for the elements that hold source and translation texts
      
          |-- Segment
          # a container that holds elements with source and translation texts
```
