---
title: FacetFieldQuery
---

# FacetFieldQuery

## Query

```gql
query FacetFieldQuery($input: FieldFacetInput) {
  facetField(input: $input) {
    fieldName
    fieldLabel
    facets {
      value
      count
      fq
    }
  }
}
```

## Variables

```json
{
  "input": {
    "field": "family",
    "q": "*:*",
    "fq": [],
    "sort": "value"
  }
}
```