---
title: ReferenceAutocompleteQuery
---

# ReferenceAutocompleteQuery

## Query

```gql
query ReferenceAutocompleteQuery($q: String!) {
  suggestions: referenceAutocomplete(q: $q) {
    id
    quickRef
    author {
      id
      name
    }
    publicationYear
    referenceStringHtml
  }
}
```

## Variables

```json
{
  "q": "Walsh 1994"
}
```