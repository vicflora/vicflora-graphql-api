---
title: VbaTaxaListItemsUnmatchedQuery
---

# VbaTaxaListItemsUnmatchedQuery

See: https://vicflora.rbg.vic.gov.au/api/#query-vbaTaxaListItemsUnmatched 


## Query

```gql
query VbaTaxaListItemsUnmatchedQuery($first: Int, $page: Int) {
  vbaTaxaListItemsUnmatched(first: $first, page: $page) {
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
      discipline
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
curl 'https://vicflora.rbg.vic.gov.au/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'Origin: chrome-extension://flnheeellpciglgpaodhkhmapeljopja' --data-binary '{"query":"query VbaTaxaListItemsUnmatchedQuery($first:Int,$page:Int){vbaTaxaListItemsUnmatched(first:$first,page:$page){paginatorInfo{count total currentPage lastPage perPage}data{id taxonType scientificName discipline}}}","variables":{"first":1000}}' --compressed
```