---
title: ParentQuery
---

# ParentQuery

## Query

```gql
query ($id: ID!) {
  parent: taxonConcept(id: $id) {
    id
    taxonName {
      id
      fullName
      rank
    }
    taxonRank
  }
}
```

## Variables

```json
{
  "id": "693441b2-4c94-4757-83ef-b62f6f894c6e"
}
```