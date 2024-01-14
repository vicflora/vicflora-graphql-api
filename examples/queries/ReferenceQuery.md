---
title: ReferenceQuery
---

# ReferenceQuery

## Query

```gql
query ($id: ID!) {
  reference(id: $id) {
    id
    referenceType
    author {
      id
      name
    }
    contributors {
      contributorRole
      agent {
        id
        name
      }
      sequence
    }
    publicationYear
    title
    edition
    journal {
      id
      referenceString
    }
    book {
      id
      author {
        id
        name
      }
      publicationYear
      referenceString
    }
    volume
    issue
    pageStart
    pageEnd
    pages
    numberOfPages
    publisher
    placeOfPublication
    isbn
    issn
    doi
  }
}
```