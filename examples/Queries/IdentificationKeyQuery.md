---
title: IdentificationKeyQuery
---

# IdentificationKeyQuery

## Query

```gql
query IdentificationKeyQuery($id: ID!) {
  identificationKey(id: $id) {
    id
    title
    taxonomicScope
    geographicScope
    created
    modified
  }
}
```

## Variables

```json
{
  "id": 2142
}
```