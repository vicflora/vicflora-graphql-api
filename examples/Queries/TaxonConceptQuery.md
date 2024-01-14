---
title: TaxonConceptQuery
---

# TaxonConceptQuery

```gql
#import "~/graphql/fragments/taxonConceptFields.gql"

query TaxonConceptQuery($id: ID!) {
  taxonConcept(id: $id) {
    id
    taxonName {
      ...taxonNameFields
      publishedIn {
        id
        referenceType
        title
        publicationYear
        volume
        pages
        quickRef
        referenceStringHtml
      }
      apniName {
        id
        apniNumber
      }
    }
    accordingTo {
      id
      quickRef
      referenceStringHtml
      author {
        id
        name
      }
      publicationYear
    }
    publicationStatus
    acceptedConcept {
      ...taxonConceptFields
    }
    synonymUsages {
      ...taxonConceptFields
    }
    misapplications {
      ...taxonConceptFields
      accordingTo {
        id
        title
      }
    }
    taxonomicStatus
    occurrenceStatus
    endemic
    establishmentMeans
    degreeOfEstablishment
    hasIntroducedOccurrences
    epbc
    ffg
    remarks

    createdBy {
      name
    }
    createdAt
    modifiedBy {
      name
    }
    updatedAt
    version
    heroImage {
      thumbnailUrl
      previewUrl
    }
    hasSpecimenImages

    mapLinks {
      profileMap
      distributionMap
      mapSource
    }

    preferredVernacularName {
      id
      name
    }

    currentProfile {
      id
      profile
      source {
        id
        referenceStringHtml
      }
      creator {
        lastName
        firstName
      }
      created
      updatedBy {
        lastName
        firstName
      }
      modified
    }
    taxonTreeDefItem {
      id
      name
      rankId
    }
    taxonRank
    parent {
      id
      taxonName {
        id
        fullName
        authorship
      }
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
    identificationKeys {
      id
      title
      taxonomicScope
      geographicScope
    }
    matrixKeys {
      id
      title
      relativePath
    }
    references {
      id
      reference {
        id
        referenceStringHtml
      }
    }
    floraLinks {
      id
      flora
      url
      icon
      sortOrder
    }
    changes {
      id
      to {
        ...taxonConceptFields
      }
      changeType
      changeSource {
        quickRef
      }
      createdBy {
        name
      }
      createdAt
    }
    vernacularNames {
      id
      name
      isPreferred
      nameUsage
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
  "id": "dfe52d12-cc3f-4620-8a9b-ab8361322615"
}
```