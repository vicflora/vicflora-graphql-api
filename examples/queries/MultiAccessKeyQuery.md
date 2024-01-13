---
title: MultiAccessKeyQuery
---

# MultiAccessKeyQuery

## Query

```gql
query MultiAccessKeyQuery($id: ID!) {
  multiAccessKey(id: $id) {
    id
    title
    description
    characterGroups {
      id
      type
      name
      description
      children {
        id
        name
      }
    }
    characters {
      id
      type
      characterType
      name
      description
      states {
        id
        name
        description
      }
    }
  }
}
```

## Variables

```json
{
  "id": "115cc464-6167-4b50-9c3a-72f0bc8ff745"
}
```