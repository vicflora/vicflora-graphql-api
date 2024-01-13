---
title: TaxonConceptSpecimenImagesQuery
---

# TaxonConceptSpecimenImagesQuery

## Query

```gql
query TaxonConceptSpecimenImagesQuery(
  $id: ID!
  $first: Int = 24
  $page: Int = 1
) {
  taxonConceptSpecimenImages(taxonConceptId: $id, first: $first, page: $page) {
    data {
      id
      alaImageUuid
      thumbnailUrl
      catalogNumber
      title
      caption
    }
    paginatorInfo {
      ...paginatorInfoFields
    }
  }
}
fragment paginatorInfoFields on PaginatorInfo {
  count
  total
  perPage
  firstItem
  currentPage
  lastPage
  hasMorePages
}
```

## Variables

```json
{
  "id": "dd6d3616-c231-429b-a75a-decff7a1661b"
}
```