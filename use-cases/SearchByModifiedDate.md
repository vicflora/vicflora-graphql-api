---
title: Search by modification date
---

# Search by modification date

**Query**

```graphql
query searchQuery($input: SearchInput!) {
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
      nameAccordingTo
      media
      created
      modified
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

**Variables**

```json
{
  "input": {
    "q":"modified:[2022-01-01T00:00:00Z TO *]",
    "rows":50,
    "fq":[],
    "page":1,
    "facetLimit":20,
    "facetField":["taxonomic_status","occurrence_status","establishment_means","degree_of_establishment","taxon_rank","family"]}
}
```

**cURL**

```sh
curl 'https://vicflora.rbg.vic.gov.au/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'Origin: chrome-extension://flnheeellpciglgpaodhkhmapeljopja' --data-binary '{"query":"query searchQuery($input:SearchInput!){search(input:$input){docs{id taxonRank acceptedNameUsage acceptedNameUsageId acceptedNameUsageAuthorship preferredVernacularName scientificName scientificNameAuthorship family taxonomicStatus nameAccordingTo media created modified}meta{params{q fq fl rows}pagination{lastPage total currentPage}}facetFields{fieldName fieldLabel facets{value count fq}}}}","variables":{}}' --compressed
```