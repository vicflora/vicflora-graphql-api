---
title: TaxonNameQuery
---

# TaxonNameQuery

## Query

```gql
query TaxonNameQuery($id: ID!) {
  taxonName(id: $id) {
    id
    rank
    parent {
      id
      fullName
      rank
    }
    namePart
    fullName
    authorship
    nameType
    protologue {
      id
      title
      volume
      issue
      pages
      publicationYear
      referenceString
    }
  }
}
```

## Variables

```json

```