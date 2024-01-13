---
title: DownloadSearchResultQuery
---

# DownloadSearchResultQuery

## Query

```gql
query DownloadSearchResultQuery($input: DownloadInput) {
  download(input: $input) {
    data
  }
}
```

## Variables

```json
{
  "input": {
    "q": "*:*",
    "fq": []
  }
}
```