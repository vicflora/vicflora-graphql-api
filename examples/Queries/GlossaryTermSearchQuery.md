---
title: GlossaryTermSearchQuery
---

# GlossaryTermSearchQuery

The normal `search` query can be used to look for glossary terms (or any word really) in descriptions in VicFlora.

## Query

```gql
query GlossaryTermSearhQuery($input: SearchInput!) {
  search(input: $input) {
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
    docs {
      id
      scientificName
      description
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

The `docs` part in the query has been slightly changed from the query in VicFlora. In VicFlora we only need the `id`; for the purpose of this example, I have also added `scientificName` and `description`.

## Variables

```json
{
  "input": {
    "q": "description:acuminate",
    "facetField": [
      "family",
      "genus",
      "species"
    ],
    "rows": 50,
    "facetLimit": -1,
    "facetSort": "count"
  }
}
```