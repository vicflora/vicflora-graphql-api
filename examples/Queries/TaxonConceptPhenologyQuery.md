---
title: TaxonConceptPhenologyQuery
---

# TaxonConceptPhenologyQuery

## Query

```gql
query TaxonConceptPhenologyQuery($id: ID!) {
  taxonConceptPhenology(taxonConceptId: $id) {
    month
    total
    buds
    flowers
    fruit
  }
}
```

## Variables

```json
{
  "id": "bf0d01ed-572f-4fe1-8145-c56307955cc5"
}
```