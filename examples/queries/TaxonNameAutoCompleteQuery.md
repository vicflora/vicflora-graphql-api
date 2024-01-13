---
title: TaxonNameAutoCompleteQuery
---

# TaxonNameAutoCompleteQuery

## Query

```gql
query TaxonNameAutoCompleteQuery($q: String!) {
  suggestions: taxonNameAutocomplete(q: $q) {
    id
    fullName
    authorship
  }
}
```

## Variables

```json
{
  "q": "Dicr"
}
```