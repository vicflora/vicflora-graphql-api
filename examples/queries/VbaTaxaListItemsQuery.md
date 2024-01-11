---
title: VbaTaxaListItemsQuery
---

# VbaTaxaListItemsQuery

See: https://vicflora.rbg.vic.gov.au/api/#query-vbaTaxaListItems

**Query**

```graphql
query VbaTaxaListItemsQuery($first: Int, $page: Int) {
  vbaTaxaListItems(first: $first, page: $page) {
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

**Variables**

```json
{
  "first": 1000,
  "page": 1
}
```

**cURL**

```sh
curl 'https://vicflora.rbg.vic.gov.au/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'Origin: chrome-extension://flnheeellpciglgpaodhkhmapeljopja' --data-binary '{"query":"query VbaTaxaListItemsQuery($first:Int,$page:Int){vbaTaxaListItems(first:$first,page:$page){paginatorInfo{count total currentPage lastPage perPage}data{id taxonType scientificName taxonName{id fullName authorship taxonConcepts{id taxonomicStatus acceptedConcept{id taxonName{id fullName authorship}}}}}}}","variables":{"first":1000,"page":1}}' --compressed
```