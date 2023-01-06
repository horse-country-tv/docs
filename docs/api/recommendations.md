---
sidebar_position: 3
---

# Recommendations

## GET `/recommendations`

The **GET** `/recommendations` endpoint is used to retrieve customised user recommendations.

#### Headers

* **Accept**: `application/json`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "data": [
        {
            "id": 24052,
            "parent_id": null,
            "type": "show",
            "handler": "kaltura",
            "handler_type": "media_entry",
            "handler_id": "1_wll3007o",
            "name": "Phillip Dutton Equitana Clinic",
            "title": {
                "en": "Phillip Dutton Equitana Clinic"
            },
            "description": {
                "en": "Three time Olympic medalist and Eventer Phillip Dutton presents a clinic from the Equitana North American forum. (S1, Ep 1/1)"
            },
            "weight": 1,
            "thumbnail": "https://cfvod.kaltura.com/p/1934501/sp/193450100/thumbnail/entry_id/1_wll3007o/version/100091",
            "thumbnail_handler": "kaltura",
            "keywords": "",
            "pricing": null,
            "inplayer_asset_id": null,
            "purchaseable": 0,
            "start_date": "2022-03-01T00:00:00.000000Z",
            "end_date": "2024-03-01T00:00:00.000000Z",
            "countries_include": null,
            "countries_exclude": null,
            "created_at": "2022-09-15T00:00:00.000000Z",
            "updated_at": "2022-11-12T01:58:21.000000Z",
            "deleted_at": null,
            "link": "http://dev.horseandcountry.localhost/shows/1_wll3007o",
            "recent": true,
            "currency": null,
            "price": null,
            "price_formatted": null,
            "plans": {
                "107785": {
                    "id": "107785",
                    "kaltura_name": "2674958 - HnC Plus Monthly"
                },
                "107814": {
                    "id": "107814",
                    "kaltura_name": "2674957 - HnC Plus Annual"
                },
                "107817": {
                    "id": "107817",
                    "kaltura_name": "2674945 - HnC Plus Gold"
                },
                "111607": {
                    "id": "111607",
                    "kaltura_name": "2868400 - HnC Plus Gold Monthly"
                }
            }
        }
    ]
}
 ```

