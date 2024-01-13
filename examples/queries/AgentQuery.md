---
title: AgentQuery
---

# AgentQuery

## Query

```gql
query AgentQuery($id: ID!) {
  agent(id: $id) {
    id
    agentType
    name
    lastName
    firstName
    initials
    members {
      sequence
      member {
        id
        name
        lastName
        firstName
        initials
      }
    }
  }
}
```

## Variables

```json
{
  "id": "db33864e-6a54-4c9e-9254-bbe7677e66af"
}
```