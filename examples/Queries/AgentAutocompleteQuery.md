---
title: AgentAutocompleteQuery
---

# AgentAutocompleteQuery

## Query

```gql
query AgentAutocompleteQuery($q: String!) {
  suggestions: agentAutocomplete(q: $q) {
    id
    agentType
    name
  }
}
```

## Variables

```json
{
  "q": "Wal"
}
```
