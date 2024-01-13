---
title: TaxonConceptImagesQuery
---

# TaxonConceptImagesQuery

## Query

```gql
query TaxonConceptImagesQuery($id: ID!, $first: Int = 24, $page: Int = 1) {
  taxonConceptImages(taxonConceptId: $id, first: $first, page: $page) {
    data {
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