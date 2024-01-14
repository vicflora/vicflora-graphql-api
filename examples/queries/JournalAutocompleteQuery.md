---
title: JournalAutocompleteQuery
---

# JournalAutocompleteQuery

## Query

```gql
query JournalAutocompleteQuery($q: String!) {
  suggestions: journalAutocomplete(q: $q) {
    id
    referenceString
  }
}
```

## Variables

```json

```