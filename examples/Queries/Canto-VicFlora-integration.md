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
          "id": "32894",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/2dfq5mhrth3k14csn2o1nvj572-20240329095657356.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/2dfq5mhrth3k14csn2o1nvj572-20240329095657356.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/2dfq5mhrth3k14csn2o1nvj572-20240329095657356.jpg",
          "w": 4080,
          "h": 2762,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Dunn, Ilma, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-03-29",
          "creator": "Dunn, Ilma",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "32895",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/u91v4jc0b51jh5ah21l583vg3m-20240329095655638.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/u91v4jc0b51jh5ah21l583vg3m-20240329095655638.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/u91v4jc0b51jh5ah21l583vg3m-20240329095655638.jpg",
          "w": 4080,
          "h": 2754,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Dunn, Ilma, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-03-29",
          "creator": "Dunn, Ilma",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "32896",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/bq1tiog4250q51bf4n9u3cvn2c-20240329095652139.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/bq1tiog4250q51bf4n9u3cvn2c-20240329095652139.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/bq1tiog4250q51bf4n9u3cvn2c-20240329095652139.jpg",
          "w": 4080,
          "h": 2771,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Dunn, Ilma, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-03-29",
          "creator": "Dunn, Ilma",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "32903",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/hg45899gml6blf4n0b9f0r8n4l.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/hg45899gml6blf4n0b9f0r8n4l.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/hg45899gml6blf4n0b9f0r8n4l.jpg",
          "w": 4080,
          "h": 2756,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Dunn, Ilma, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-03-29",
          "creator": "Dunn, Ilma",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Victoria",
          "subtype": "Photograph"
        },
        {
          "id": "32904",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/fn4fumu0q51ub62viqfvfev43q.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/fn4fumu0q51ub62viqfvfev43q.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/fn4fumu0q51ub62viqfvfev43q.jpg",
          "w": 4080,
          "h": 2775,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Dunn, Ilma, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-03-29",
          "creator": "Dunn, Ilma",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "33237",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/9lb1jk3q49639fjsoqsbfen225-20240329092737874.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/9lb1jk3q49639fjsoqsbfen225-20240329092737874.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/9lb1jk3q49639fjsoqsbfen225-20240329092737874.jpg",
          "w": 3849,
          "h": 2608,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Clarke, Ian C., <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2021-07-15",
          "creator": "Clarke, Ian C.",
          "license": null,
          "copyrightOwner": "Royal Botanic Gardens Victoria Board",
          "subtype": "Photograph"
        },
        {
          "id": "33799",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/ta1m142vtd2ad8ktaqhu913p3l-20240328043151508.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/ta1m142vtd2ad8ktaqhu913p3l-20240328043151508.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/ta1m142vtd2ad8ktaqhu913p3l-20240328043151508.jpg",
          "w": 3456,
          "h": 2304,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Lay, Geoff, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2006-09-17",
          "creator": "Lay, Geoff",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Geoff Lay",
          "subtype": "Photograph"
        },
        {
          "id": "34484",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/a89i9uehu138n337upc583403s-20240328040137145.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/a89i9uehu138n337upc583403s-20240328040137145.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/a89i9uehu138n337upc583403s-20240328040137145.jpg",
          "w": 5316,
          "h": 3479,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Elliot, Gwen & Rodger, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2012-12-24",
          "creator": "Elliot, Gwen & Rodger",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Gwen & Rodger Elliot",
          "subtype": "Photograph"
        },
        {
          "id": "34496",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/3pbdql63j16bd30kkdclfl2c5j-20240328040126793.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/3pbdql63j16bd30kkdclfl2c5j-20240328040126793.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/3pbdql63j16bd30kkdclfl2c5j-20240328040126793.jpg",
          "w": 3479,
          "h": 5396,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Elliot, Gwen & Rodger, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2012-12-24",
          "creator": "Elliot, Gwen & Rodger",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Gwen & Rodger Elliot",
          "subtype": "Photograph"
        },
        {
          "id": "34711",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/3lkgsru4rl2ir004qhe1bps62g-20240328035759852.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/3lkgsru4rl2ir004qhe1bps62g-20240328035759852.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/3lkgsru4rl2ir004qhe1bps62g-20240328035759852.jpg",
          "w": 3008,
          "h": 2008,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Elliot, Gwen & Rodger, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2007-09-16",
          "creator": "Elliot, Gwen & Rodger",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Gwen & Rodger Elliot",
          "subtype": "Photograph"
        },
        {
          "id": "44437",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/s42t50oqjh3tdcb0973cje0f2n-20240328024106129.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/s42t50oqjh3tdcb0973cje0f2n-20240328024106129.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/s42t50oqjh3tdcb0973cje0f2n-20240328024106129.jpg",
          "w": 3081,
          "h": 2149,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Neil Blair, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2013-08-27",
          "creator": "Neil Blair",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "44439",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/li3e58ec7h1bt5nq9jnjttf31i-20240328024105925.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/li3e58ec7h1bt5nq9jnjttf31i-20240328024105925.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/li3e58ec7h1bt5nq9jnjttf31i-20240328024105925.jpg",
          "w": 856,
          "h": 735,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Blair, Neil, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2013-05-26",
          "creator": "Blair, Neil",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "44442",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/3trnun41c16jf5d02cagkuvl2n-20240328024105359.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/3trnun41c16jf5d02cagkuvl2n-20240328024105359.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/3trnun41c16jf5d02cagkuvl2n-20240328024105359.jpg",
          "w": 2927,
          "h": 818,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Blair, Neil, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2013-07-10",
          "creator": "Blair, Neil",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "44443",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/6qlimqujk970dcooru6hi0587d-20240328024104342.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/6qlimqujk970dcooru6hi0587d-20240328024104342.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/6qlimqujk970dcooru6hi0587d-20240328024104342.jpg",
          "w": 2119,
          "h": 2885,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Blair, Neil, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2013-09-12",
          "creator": "Blair, Neil",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Board",
          "subtype": "Photograph"
        },
        {
          "id": "52964",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/qitof528l16v36ib2i5cvmpe0j-20240327131712481.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/qitof528l16v36ib2i5cvmpe0j-20240327131712481.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/qitof528l16v36ib2i5cvmpe0j-20240327131712481.jpg",
          "w": 2448,
          "h": 3264,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Freestone, Marc, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2015-11-08",
          "creator": "Freestone, Marc",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Victoria",
          "subtype": "Photograph"
        },
        {
          "id": "54271",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/a2o778rtf14bncujhm9587lh18-20240327080338990.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/a2o778rtf14bncujhm9587lh18-20240327080338990.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/a2o778rtf14bncujhm9587lh18-20240327080338990.jpg",
          "w": 3201,
          "h": 1939,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Source:</b> Mayfield, E. (2003). Flora of the Otway Plain and Ranges. 2: daisies, heaths, peas, saltbushes, sundews, wattles and other shrubby and herbaceous dicotyledons. CSIRO Publishing, Collingwood.<br/><b>Illustration:</b> Mayfield, Enid, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2017-06-16",
          "creator": "Mayfield, Enid",
          "license": null,
          "copyrightOwner": "Enid Mayfield",
          "subtype": "Illustration"
        },
        {
          "id": "57269",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/541tc8kq791vd4ir411s4a4845-20240327104019032.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/541tc8kq791vd4ir411s4a4845-20240327104019032.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/541tc8kq791vd4ir411s4a4845-20240327104019032.jpg",
          "w": 1208,
          "h": 827,
          "caption": "<i>Acacia melanoxylon</i>. b. branch with phyllode detail; inflorescence; seed.<br/><b>Illustration:</b> Moir, M., National Herbarium of Victoria, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-03-27",
          "creator": "Moir, M., National Herbarium of Victoria",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": "Royal Botanic Gardens Victoria",
          "subtype": "Illustration"
        },
        {
          "id": "57472",
          "previewUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/preview/pak1d1l76d5hn43ffi8r1v2o2g-20240320015951803.jpg",
          "thumbnailUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/thumb/pak1d1l76d5hn43ffi8r1v2o2g-20240320015951803.jpg",
          "highestResUrl": "https://vicflora-cdn.rbg.vic.gov.au/assets/canto/highestres/pak1d1l76d5hn43ffi8r1v2o2g-20240320015951803.jpg",
          "w": 1600,
          "h": 1200,
          "caption": "<i>Acacia melanoxylon</i><br/><b>Photo:</b> Hare, Robert, <a href='https://creativecommons.org/licenses/by-nc-sa/4.0'>CC BY-NC-SA 4.0</a>",
          "creationDate": "2024-03-20",
          "creator": "Hare, Robert",
          "license": "CC BY-NC-SA 4.0",
          "copyrightOwner": null,
          "subtype": "Photograph"
        }
      ],
      "paginatorInfo": {
        "count": 18,
        "total": 18,
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

This produces the images for
https://vicflora.rbg.vic.gov.au/flora/taxon/0c8e21a6-fe09-4835-84e1-d9531ad24728.
The response from the API you will be setting up should look like this (does not
have to be exactly the same).

There are more fields documented for
[Image](https://vicflora.rbg.vic.gov.au/apidocs/#definition-Image) but the
complete result should be the same fields that you provide now. You can use the
same labels as we are using now too.

At the moment we do not need any further querying
capability, but that could be an addition in the future.

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
