---
title: SearchQuery
---

# SearchQuery

## Query

```gql
query SearchQuery($input: SearchInput!) {
  search(input: $input) {
    docs {
      id
      taxonRank
      acceptedNameUsage
      acceptedNameUsageId
      acceptedNameUsageAuthorship
      preferredVernacularName
      scientificName
      scientificNameAuthorship
      family
      taxonomicStatus
      occurrenceStatus
      nameAccordingTo
    }
    meta {
      params {
        q
        fq
        fl
        rows
      }
      pagination {
        lastPage
        total
        currentPage
      }
    }
    facetFields {
      fieldName
      fieldLabel
      facets {
        value
        count
        fq
      }
    }
  }
}
```

## Variables

```json
{
  "input": {
    "q": "*:*",
    "rows": 50,
    "fq": [],
    "page": 1,
    "facetLimit": 20,
    "facetField": [
      "taxonomic_status",
      "occurrence_status",
      "establishment_means",
      "degree_of_establishment",
      "taxon_rank",
      "family"
    ]
  }
}
```