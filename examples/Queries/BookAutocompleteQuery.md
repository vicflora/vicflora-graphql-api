---
title: BookAutocompleteQuery
---

# BookAutocompleteQuery

## Query

```gql
query BookAutocompleteQuery($q: String!) {
  suggestions: bookAutocomplete(q: $q) {
    id
    referenceStringHtml
  }
}
```

## Variables

```json

```