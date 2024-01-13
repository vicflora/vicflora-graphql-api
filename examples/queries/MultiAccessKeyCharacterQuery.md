---
title: MultiAccessKeyCharacterQuery
---

# MultiAccessKeyCharacterQuery

## Query

```gql
query MultiAccessKeyCharacterQuery($id: ID!) {
  multiAccessKeyCharacter(id: $id) {
    id
    type
    characterType
    name
    description
    key {
      id
      title
    }
    states {
      id
      name
      description
      images {
        id
        previewUrl
        thumbnailUrl
        w: pixelXDimension
        h: pixelYDimension
        caption
        assetCreationDate
        creator
        license
        copyrightOwner
        subtype
      }
    }
    unit {
      name
    }
  }
}
```

## Variables

```json
{
  "id": "3c89576e-e6fb-4d33-aa3c-feed71cb89be"
}
```