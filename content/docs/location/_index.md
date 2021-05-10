---
title: Location
weight: 2
---

There are two location functions, `reverseGeocode` and `geocode`. The geocode service allows you to find the approximate coordinates for a given street address. The reverse geocoding service instead takes in a pair of coordinates and returns the approximate address at which that point is located.

**Response bodies for both ProcessGeocode and ProcessReverseGeocode are similar and contain similar members**. The response body gets or sets the response, which contains the results of geocoding or reverse geocoding.

### GeocodeResponseBody Members

| Element  | Definition                                                                                                                         |
| -------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Location | A list <> of [GeocodeOutputLocation](../shared-api-members/#location) objects. Gets or sets the collection of locations of geocode |
