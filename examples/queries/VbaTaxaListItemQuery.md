---
title: VbaTaxaListItemQuery
---

# VbaTaxaListItemQuery

See: https://vicflora.rbg.vic.gov.au/api/#query-vbaTaxaListItem

## Query

```graphql
query VbaTaxaListItemQuery($id: ID!) {
  vbaTaxaListItem(id: $id) {
    id
    scientificName
    commonName
    authority
    restriction
    origin
    taxonType
    lifeForm
    nvisGrowthForm
    fireResponse
    treaty
    discipline
    taxonLevel
    fisSpeciesNumber
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
```

## Variables

```json
{
  "id": "500657"
}
```

## cURL

```sh
curl 'https://vicflora.rbg.vic.gov.au/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'Origin: chrome-extension://flnheeellpciglgpaodhkhmapeljopja' --data-binary '{"query":"query VbaTaxaListItemQuery($id:ID!){vbaTaxaListItem(id:$id){id scientificName commonName authority restriction origin taxonType lifeForm nvisGrowthForm fireResponse treaty discipline taxonLevel fisSpeciesNumber taxonName{id fullName authorship taxonConcepts{id taxonomicStatus acceptedConcept{id taxonName{id fullName authorship}}}}}}","variables":{"id":"500657"}}' --compressed
```