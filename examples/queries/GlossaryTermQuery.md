---
title: GlossaryTermQuery
---

# GlossaryTermQuery

## Query

```gql
query GlossaryTermQuery($name: String = "abaxial") {
  term: glossaryTermsByName(name: $name) {
    id
    name
    definition
    relationships {
      id
      relationshipType {
        id
        name
      }
      relatedTerm {
        id
        name
        definition
      }
    }
    images {
      id
      imageUrl
      rights
      title
      caption
      source
    }
  }
}
```

## Variables

```json
{
  "name": "dichasium"
}
```