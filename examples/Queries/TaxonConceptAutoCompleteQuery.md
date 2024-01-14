---
title: TaxonConceptAutoCompleteQuery
---

# TaxonConceptAutoCompleteQuery

## Query

```gql
query TaxonConceptAutoCompleteQuery($q: String!) {
  suggestions: taxonConceptAutocomplete(q: $q) {
    id
    taxonName {
      id
      fullName
      authorship
    }
  }
}
```

## Variables

```json

```