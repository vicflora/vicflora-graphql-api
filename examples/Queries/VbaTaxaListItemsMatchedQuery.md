---
title: VbaTaxaListItemsMatchedQuery
---

# VbaTaxaListItemsMatchedQuery

See: https://vicflora.rbg.vic.gov.au/api/#query-vbaTaxaListItemsMatched

## Query

```gql
query VbaTaxaListItemsMatchedQuery($first: Int, $page: Int) {
  vbaTaxaListItemsMatched(first: $first, page: $page) {
    paginatorInfo {
      count
      total
      currentPage
      lastPage
      perPage
    }
    data {
      id
      taxonType
      scientificName
      taxonName {
        id
        fullName
        authorship
        taxonConcepts {
          id
          taxonomicStatus
          acceptedConcept {
            id
            taxonName {
              id
              fullName
              authorship
            }
          }
        }
      }
    }
  }
}
```

## Variables

```json
{
  "first": 1000
}
```

## cURL

```sh
curl 'https://vicflora.rbg.vic.gov.au/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'Origin: chrome-extension://flnheeellpciglgpaodhkhmapeljopja' --data-binary '{"query":"query VbaTaxaListItemsMatchedQuery($first:Int,$page:Int){vbaTaxaListItemsMatched(first:$first,page:$page){paginatorInfo{count total currentPage lastPage perPage}data{id taxonType scientificName taxonName{id fullName authorship taxonConcepts{id taxonomicStatus acceptedConcept{id taxonName{id fullName authorship}}}}}}}","variables":{"first":1000}}' --compressed
```