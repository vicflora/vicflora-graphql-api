---
title: PersonAutocompleteQuery
---

# PersonAutocompleteQuery

## Query

```gql
query PersonAutocompleteQuery($q: String!) {
  suggestions: personAutocomplete(q: $q) {
    id
    agentType
    name
  }
}
```

## Variables

```json
{
  "q": "Mess"
}
```