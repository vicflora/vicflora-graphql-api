---
title: ChecklistMapInfoQuery
---

# ChecklistMapInfoQuery

This query collects feature information from the four overlays that are used in
VicFlora for a point that is clicked on the map on the
[Checklist](https://vicflora.rbg.vic.gov.au/checklist/) page in VicFlora.

## Query

```gql
query ChecklistMapInfoQuery($latitude: Float!, $longitude: Float!) {
  parksOrReserves: parkReservesByPoint(
    latitude: $latitude
    longitude: $longitude
  ) {
    properties {
      name
      label
      slug
    }
  }

  bioregions: bioregionsByPoint(latitude: $latitude, longitude: $longitude) {
    properties {
      name
      label
      slug
    }
  }

  localGovernmentAreas: localGovernmentAreasByPoint(
    latitude: $latitude
    longitude: $longitude
  ) {
    properties {
      name
      label
      slug
    }
  }

  registeredAboriginalParties: registeredAboriginalPartiesByPoint(
    latitude: $latitude
    longitude: $longitude
  ) {
    properties {
      name
      label
      slug
    }
  }
}
```

## Variables

An object with the latitude and longitude that can be used here will show in the
console if you click on the map on the
[Checklist](https://vicflora.rbg.vic.gov.au/checklist/) page in VicFlora.

```json
{
  "latitude": -38.97799137141177,
  "longitude": 146.35187432169917
}
```