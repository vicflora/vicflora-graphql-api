---
title: TaxonOccurrencesAtPointQuery
---

# TaxonOccurrencesAtPointQuery

## Query

```gql
query TaxonOccurrencesAtPointQuery(
  $taxonConceptId: ID!
  $latitude: Float!
  $longitude: Float!
) {
  taxonOccurrencesAtPoint(
    taxonConceptId: $taxonConceptId
    latitude: $latitude
    longitude: $longitude
    first: 500
  ) {
    paginatorInfo {
      total
      perPage
      currentPage
    }
    data {
      properties {
        uuid
        dataSource
        collection
        catalogNumber
        recordedBy
        recordNumber
        eventDate
        scientificName
        occurrenceStatus
        establishmentMeans
        degreeOfEstablishment
      }
    }
  }
}
```

## Variables

```json
{
  "taxonConceptId": "f7bb03d4-2c19-422b-b502-9fa23e8eee71",
  "latitude": -38.752420729036515,
  "longitude": 143.51740166544917
}
```