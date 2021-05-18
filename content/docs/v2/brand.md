---
title: "Brands"
description: "Details on the Brand resource endpoint"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "v2"
weight: 110
toc: true
---

Brands in Marketplacer represent the brands for [adverts](/docs/v2/advert).

## Listing brands

This endpoint returns all brands.

### Request

    GET /api/v2/brands

### Response

<div class="alert alert-success" role="alert">
  Status 200 OK
</div>

```json
{
  "data": [
    {
      "id": 1,
      "type": "brands",
      "attributes": {
        "name": "Giant",
        "slug": "giant"
      }
    }
  ]
}
```

## Search for brands

This endpoint allows you to search for a brand by its name or by a substring of its name.

### Request

If you wish to search for the "Giant" brand, make a query like this:

    GET /api/v2/brands/search?name=Giant

If you wish to search by a substring, add the `autocomplete` parameter, like this:

    GET /api/v2/brands/search?name=Gia&autocomplete=1

### Response

<div class="alert alert-success" role="alert">
  Status 200 OK
</div>

```json
{
  "data": [
    {
      "id": 1,
      "type": "brands",
      "attributes": {
        "name": "Giant",
        "slug": "giant"
      }
    }
  ]
}
```