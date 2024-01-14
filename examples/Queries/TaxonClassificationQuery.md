---
title: TaxonClassificationQuery
---

# TaxonClassificationQuery

This query is used for the '[Browse
classification](https://vicflora.rbg.vic.gov.au/flora/classification/)' part of
VicFlora/ It re-uses the `taxonConcept` query that is used for the taxon pages,
but only requests the classification-related data.

## Query

```gql
#import "~/graphql/fragments/taxonConceptFields.gql"

query TaxonClassificationQuery($id: ID!) {
  taxonConcept(id: $id) {
    ...taxonConceptFields
    taxonTreeDefItem {
      rankId
      id
      name
    }
    parent {
      ...taxonConceptFields
    }
    children {
      ...taxonConceptFields
      taxonTreeDefItem {
        id
        name
        rankId
      }
    }
    siblings {
      ...taxonConceptFields
    }
    higherClassification {
      ...taxonConceptFields
      taxonTreeDefItem {
        id
        name
        rankId
      }
    }
  }
}
fragment taxonConceptFields on TaxonConcept {
  id
  taxonName {
    ...taxonNameFields
  }
}
fragment taxonNameFields on TaxonName {
  id
  fullName
  authorship
}
```

## Variables

```json
{
  "id": "6abc498a-70de-11e6-a989-005056b0018f"
}
```