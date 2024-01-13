---
title: Searching by date (change history)
---

# Searching by date (change history)

## How to

VicFlora does not have a UI for date and date range searches, but you can search
for them by typing a SOLR query string in the search box that tells you to fill
in a taxon name. 

The date fields that can be queried on are:

- `created`: Date the (taxon) record was first created. The census was first
  loaded on January 24, 2014, and creation dates have only been indexed for
  records that were created after that.
- `modified`: Date the last change to the record occurred. The changes that have
  been indexed are those that mean concept changes, i.e. a name being
  synonymised or re-established. These changes go back all the way to 2000
  (6<sup>th</sup> edition of the Census). 
- `last_edit`: Date a record was either `created` or last `modified`.
- `profile_created`: Date when a profile was created for a taxon. The
  descriptions from the *Flora of Victoria* were loaded on May 1, 2014, so the
  dates go only back to the day after that.
- `profile_updated`: Date the last version of a taxon treatment has been
  created, if there is more than one version. VicFlora editors can decide
  whether the changes they make to a profile warrant a new version or not, so
  that minor edits can be made without creating a new version. The creator of
  the latest version and the date this version was created, are what is given
  under 'Updated by' on the taxon pages in VicFlora.
- The `created_year`, `created_year_month`, `changed_year`,
  `changed_year_month`, `profile_created_year`, `profile_created_year_month`,
  `profile_updated_year` and `profile_updated_year_month` can also be searched
  on but were intended as and are more useful as facet fields.

Dates in SOLR have to be UTC timestamps, so include the date `YYYY-mm-dd`, a `T`
to indicate that there is a time coming, the time in hours, minutes and seconds,
`hh:ii:ss`, and the timezone, which can only be `Z` (for Zulu, i.e. UTC or GMT).
So, today is `2024-01-15T00:00:00Z`. It should be noted that Australian Eastern
Standard Time (AEST) is ten hours ahead of UTC, so, if you are an early riser,
records you entered might seem to have been entered the day before.

Date ranges are given in square brackets, like this:

```
[2023-07-01T00:00:00Z TO 2024-01-01T00:00:00Z]
```

The wildcard character `*` can be used to indicate the beginning of time, if it
comes before the `TO`, or the current time if it comes after. So,
`[2024-01-01T00:00:00Z TO *]` is this year so far. `[* TO *]`, or just `*`,
gives all records that have a value in the date field.

Fields and values are separated by a colon, `:`, like in the following examples:

- Taxon records created in 2023:

  ```
  created:[2023-01-01T00:00:00Z TO 2024-01-01T00:00:00Z]
  ```

  This works as well:

  ```
  created_year:2023
  ```

- Taxon records created or changed from the start of 2024:

  ```
  last_edit:[2024-01-01T00:00:00Z TO *]
  ```
- Treatments created in the last quarter of 2023:
  
  ```
  profile_created:[2023-10-01T00:00:00Z TO 2024-01-01T00:00:00Z]
  ```
- Treatments updated in the last quarter of 2023:
  
  ```
  profile_updated:[2023-10-01T00:00:00Z TO 2024-01-01T00:00:00Z]
  ```

No warnings are given on the page if an invalid search string is entered. In
fact, nothing will happen at all. The browser console will show a GraphQL error
though, so you can open that (`CTRL+SHIFT+I` and then select `Console`) if you
want to see what is going on.

## Under the hood

This is how it is done in the GraphQL API.

### Query

The fields that need to be included in the output should be listed under `docs`
in GraphQL Query Langauage (so inside curly braces and with only whitespace
separating them). This is what goes in the `fl` parameter, as a comma-separated
string, in the SOLR query string and are the fields that will be available for
use in the search result items.

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

### Variables

Any of the search strings listed above can be given as the value for `q`. The
facet fields that you want to show go in the `facetField` array. The facet
fields you select in the 'Filter Configuration' window on the Search page in
VicFlora go in here.

```json
{
  "input": {
    "q": "modified:[2022-01-01T00:00:00Z TO *]",
    "rows": 50,
    "fq": [],
    "page": 1,
    "facetLimit": 20,
    "facetField": [
      "phylum",
      "created_year",
      "created_year_month",
      "updated_year",
      "updated_year_month",
      "profile_created_year",
      "profile_created_year_month",
      "profile_updated_year",
      "profile_updated_year_month"
    ]
  }
}
```