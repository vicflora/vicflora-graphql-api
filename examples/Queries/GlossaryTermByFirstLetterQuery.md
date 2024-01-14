---
title: GlossaryTermsByFirstLetterQuery
---

# GlossaryTermsByFirstLetterQuery

## Query

```gql
query GlossaryTermsByFirstLetterQuery($firstLetter: String = "A") {
  terms: glossaryTermsByName(name: $firstLetter) {
    id
    name
  }
}
```

## Variables

```json
{
  "firstLetter": "D"
}
```