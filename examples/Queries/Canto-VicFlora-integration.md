# Canto–VicFlora integration

*Instructions for FFM, 2024-10-25*

**TLDR;**

At the end of the document is a query that will get you the entire lookup table.
You only need the lookup table for tha hierarchy, as the name matching I can do
at my end. I could use some help to set up things properly at my end too (I can
write a separate document for that).

<br/>

**Endpoint:** https://vicflora.rbg.vic.gov.au/graphql

**Documentation:** https://vicflora.rbg.vic.gov.au/apidocs

This is the API request I use to get images for a single taxon (page):

**Query** 

```graphql
query TaxonConceptImagesQuery($id: ID!, $first: Int = 24, $page: Int = 1) {
  taxonConceptImages(taxonConceptId: $id, first: $first, page: $page) {
    data {
      id
      previewUrl
      thumbnailUrl
      highestResUrl
      w: pixelXDimension
      h: pixelYDimension
      caption
      creationDate
      creator
      license
      copyrightOwner
      subtype
    }
    paginatorInfo {
      ...paginatorInfoFields
    }
  }
}
fragment paginatorInfoFields on PaginatorInfo {
  count
  total
  perPage
  firstItem
  currentPage
  lastPage
  hasMorePages
}
```

**Variables**

```json
{
  "id": "0c8e21a6-fe09-4835-84e1-d9531ad24728"
}
```

**Result**

```json
{
  "data": {
    "taxonConceptImages": {
      "data": [
        {
          "id": "53642",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/rhpon5nhil7cl7n1u8hn37lq34.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/rhpon5nhil7cl7n1u8hn37lq34.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/rhpon5nhil7cl7n1u8hn37lq34.jpg",
          "w": 835,
          "h": 864,
          "caption": "<i>Vicia tetrasperma</i>. e. fruiting stem; f. flower.<br/><b>Source:</b> Walsh, N.G.; Entwisle, T.J. (eds) (1996). Flora of Victoria Vol. 3, Dicotyledons Winteraceae to Myrtaceae. Inkata Press, Melbourne.<br/><b>Illustration:</b> Moir, M., National Herbarium of Victoria, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2017-06-15",
          "creator": "Moir, M., National Herbarium of Victoria",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": null,
          "subtype": "Illustration"
        },
        {
          "id": "59456",
          "previewUrl": null,
          "thumbnailUrl": null,
          "highestResUrl": null,
          "w": 2655,
          "h": 3744,
          "caption": "<i>Vicia tetrasperma</i><br/><b>Photo:</b> Clarke, Ian, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-08-07",
          "creator": "Clarke, Ian",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": null
        },
        {
          "id": "59582",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/dnri2b79nh0tp911hh98q3sm2h-20240708041416263.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/dnri2b79nh0tp911hh98q3sm2h-20240708041416263.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/dnri2b79nh0tp911hh98q3sm2h-20240708041416263.jpg",
          "w": 2474,
          "h": 3681,
          "caption": "<i>Vicia tetrasperma</i><br/><b>Photo:</b> Clarke, Ian, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-08-07",
          "creator": "Clarke, Ian",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": null
        },
        {
          "id": "59584",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/nr2qvhd4751fl2ug145p7och74-20240708041415828.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/nr2qvhd4751fl2ug145p7och74-20240708041415828.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/nr2qvhd4751fl2ug145p7och74-20240708041415828.jpg",
          "w": 4288,
          "h": 2848,
          "caption": "<i>Vicia tetrasperma</i><br/><b>Photo:</b> Clarke, Ian, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-08-07",
          "creator": "Clarke, Ian",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": null
        }
      ],
      "paginatorInfo": {
        "count": 4,
        "total": 4,
        "perPage": 24,
        "firstItem": 1,
        "currentPage": 1,
        "lastPage": 1,
        "hasMorePages": false
      }
    }
  }
}
```

This produces the images for https://vicflora.rbg.vic.gov.au/flora/taxon/0c8e21a6-fe09-4835-84e1-d9531ad24728.

There are more fields documented for
[Image](https://vicflora.rbg.vic.gov.au/apidocs/#definition-Image) but the
complete result should be the same fields that you provide now. You can use the
same labels as we are using now too,

<br/>

This query gets you all the information you need for a single taxon:

**Query**

```graphql
query TaxonConceptQuery($id: ID!){
  taxonConcept(id: $id) {
    ...TaxonConceptFragment
    parent {
      ...TaxonConceptFragment
    }
    higherClassification {
      ...TaxonConceptFragment
    }
  }
}
fragment TaxonConceptFragment on TaxonConcept {
  id
  taxonName {
    fullName
    authorship
  }
  taxonRank
}
```

**Variables**

```json
{
  "id": "0c8e21a6-fe09-4835-84e1-d9531ad24728"
}
```

You can do this in Postman and it will give you a cURL command (my client does
not).

Output for this query:

```json
{
  "data": {
    "taxonConcept": {
      "id": "0c8e21a6-fe09-4835-84e1-d9531ad24728",
      "taxonName": {
        "fullName": "Acacia dealbata",
        "authorship": "Link"
      },
      "taxonRank": "SPECIES",
      "parent": {
        "id": "dfe52d12-cc3f-4620-8a9b-ab8361322615",
        "taxonName": {
          "fullName": "Acacia",
          "authorship": null
        },
        "taxonRank": "GENUS"
      },
      "higherClassification": [
        {
          "id": "da1de22e-1d65-4197-9f4c-38ca39b964af",
          "taxonName": {
            "fullName": "Plantae",
            "authorship": null
          },
          "taxonRank": "KINGDOM"
        },
        {
          "id": "6abc498a-70de-11e6-a989-005056b0018f",
          "taxonName": {
            "fullName": "Tracheophyta",
            "authorship": null
          },
          "taxonRank": "PHYLUM"
        },
        {
          "id": "6ac11352-70de-11e6-a989-005056b0018f",
          "taxonName": {
            "fullName": "Magnoliopsida",
            "authorship": null
          },
          "taxonRank": "CLASS"
        },
        {
          "id": "e635c57f-06ef-4832-b4b5-b74b699e9f65",
          "taxonName": {
            "fullName": "Fabales",
            "authorship": null
          },
          "taxonRank": "ORDER"
        },
        {
          "id": "d3590e10-e8ac-4848-9e33-9fbbaf171f7a",
          "taxonName": {
            "fullName": "Fabaceae",
            "authorship": null
          },
          "taxonRank": "FAMILY"
        },
        {
          "id": "dfe52d12-cc3f-4620-8a9b-ab8361322615",
          "taxonName": {
            "fullName": "Acacia",
            "authorship": null
          },
          "taxonRank": "GENUS"
        }
      ]
    }
  }
}
```

`data.TaxonConcept.taxonName.fullName` corresponds to the 'Scientific name'
field in Canto, so that is what we match on. After our meeting, I now think it
is probably best if I do the matching at my end and store the taxon concept ID
in Canto. I would like some help to get things up properly at our end. It is not
a problem to give you access to our network to work. It is the always-open
database connection that we have now that is the problem. Doing it this way will 
also set us up nicely for further integrations in the future.

`data.TaxonConcept.higherClassification` contains the hierarchy I told you about
yesterday. The top one (kingdom) is the highest rank. If I give the UUID of a
higher-ranked taxon in the `taxonConceptImages` query, I should get all the
images of its subordinates as well.

So, the lookup table should look like this:

| id | fullName | authorship | rank | parent |
|-|-|-|-|-|
| da1de22e-1d65-4197-9f4c-38ca39b964af | Plantae |  | kingdom |  |
| 6abc498a-70de-11e6-a989-005056b0018f | Tracheophyta |  | phylum | da1de22e-1d65-4197-9f4c-38ca39b964af |
| 6ac11352-70de-11e6-a989-005056b0018f | Magnoliopsida |  | class | 6abc498a-70de-11e6-a989-005056b0018f |
| e635c57f-06ef-4832-b4b5-b74b699e9f65 | Fabales |  | order | 6ac11352-70de-11e6-a989-005056b0018f |
| d3590e10-e8ac-4848-9e33-9fbbaf171f7a | Fabaceae |  | family | e635c57f-06ef-4832-b4b5-b74b699e9f65 |
| dfe52d12-cc3f-4620-8a9b-ab8361322615 | Acacia |  | genus | d3590e10-e8ac-4848-9e33-9fbbaf171f7a |
| 0c8e21a6-fe09-4835-84e1-d9531ad24728 | Acacia dealbata | Link. | species | dfe52d12-cc3f-4620-8a9b-ab8361322615 |
| a7b5e691-0803-40d6-a1d4-dd96e54720a0 | Acacia melanoxylon | R.Br. | species | dfe52d12-cc3f-4620-8a9b-ab8361322615 |
| ... | ... | ... | ... | ... |

I use a recursive query in Eloquent to get all subordinate taxa. The code for
this is
[here](https://github.com/vicflora/vicflora-laravel/blob/main/app/Actions/GetTaxonConceptImages.php).
This requires the
[Laravel-CTE](https://packagist.org/packages/staudenmeir/laravel-cte) package.

To get the UUID–name combination for all taxa, you can currently do that only
via the Search:

**Query**

```graphql
query SearchQuery($input: SearchInput!) {
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
      taxonRank
      acceptedNameUsage
      acceptedNameUsageId
      acceptedNameUsageAuthorship
      preferredVernacularName
      scientificName
      scientificNameAuthorship
      family
      taxonomicStatus
      occurrenceStatus
      nameAccordingTo
    }
  }
}
```

**Variables**

```json
{
  "input": {
    "q": "*",
    "rows": 50,
    "page": 1
  }
}
```

or

```json
{
  "input": {}
}
```

as there are defaults for all variables.

This is what I use for the Search in VicFlora.

For the synchronisation, I am quite keen to look into the subscription (that's
the term GraphQL uses for a webhook, I think), as I have not done that before
and I think it might be useful for other consumers of VicFlora data as well. For
our purposes, however, it might be more useful to just be able to query for
changes in a certain period of time. Also, VicFlora is not huge; it will
probably take less than a minute to replace the entire lookup table. I do this
for the distribution maps, for which I have a separate Laravel app. (only I do
not have to use a web service).

The following query will give you all the data you'll ever need. And you can set
the `rows` variable to a high number like `1000` and you'll have the data in no
time. For this example, I have set it really low (`5`) and I have put in a
query, so you'll get some more meaningful data than just the first five
documents in the index.

**Query**

```graphql
query SearchQuery($input: SearchInput!) {
  search(input: $input) {
    docs {
      id
      scientificName
      scientificNameAuthorship
      taxonRank
      parentNameUsageId
      parentNameUsage
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
  }
}
```

**Variables**

```json
{
  "input": {
    "q": "genus:Acacia",
    "rows": 5,
    "page": 1
  }
}
```

**Result**

```json
{
  "data": {
    "search": {
      "docs": [
        {
          "id": "dfe52d12-cc3f-4620-8a9b-ab8361322615",
          "scientificName": "Acacia",
          "scientificNameAuthorship": null,
          "taxonRank": "genus",
          "parentNameUsageId": "d3590e10-e8ac-4848-9e33-9fbbaf171f7a",
          "parentNameUsage": "Fabaceae"
        },
        {
          "id": "588817df-2591-461b-a4c5-c5dc5d18e980",
          "scientificName": "Acacia acanthoclada",
          "scientificNameAuthorship": "F.Muell.",
          "taxonRank": "species",
          "parentNameUsageId": "dfe52d12-cc3f-4620-8a9b-ab8361322615",
          "parentNameUsage": "Acacia"
        },
        {
          "id": "792b7e3c-9d40-487d-8aec-d057fda725e1",
          "scientificName": "Acacia acanthoclada subsp. acanthoclada",
          "scientificNameAuthorship": null,
          "taxonRank": "subspecies",
          "parentNameUsageId": "588817df-2591-461b-a4c5-c5dc5d18e980",
          "parentNameUsage": "Acacia acanthoclada"
        },
        {
          "id": "63bd1b91-99f6-4eff-b093-675b249e7aad",
          "scientificName": "Acacia acinacea",
          "scientificNameAuthorship": "Lindl.",
          "taxonRank": "species",
          "parentNameUsageId": "dfe52d12-cc3f-4620-8a9b-ab8361322615",
          "parentNameUsage": "Acacia"
        },
        {
          "id": "72dd0540-6407-42f7-aa78-d90a36a66e82",
          "scientificName": "Acacia aculeatissima",
          "scientificNameAuthorship": "J.F.Macbr.   ",
          "taxonRank": "species",
          "parentNameUsageId": "dfe52d12-cc3f-4620-8a9b-ab8361322615",
          "parentNameUsage": "Acacia"
        }
      ],
      "meta": {
        "params": {
          "q": "genus:Acacia",
          "fq": null,
          "fl": [
            "id",
            "scientific_name",
            "scientific_name_authorship",
            "taxon_rank",
            "parent_name_usage_id",
            "parent_name_usage"
          ],
          "rows": 5
        },
        "pagination": {
          "lastPage": 51,
          "total": 253,
          "currentPage": 1
        }
      }
    }
  }
}
```

I will change the `parentNameUsageId` and `parentNameUsage` to `parentId` and
`parentName` respectively.
