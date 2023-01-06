---
sidebar_position: 3
---

# Recommendations

## GET `/recommendations`

The **GET** `/contents` endpoint is used to retrieve contents. For example, it can be useful when retrieving search results or when displaying a set of shows, series or episodes on a rail.

#### Headers

* **Accept**: `application/json`

#### Query Parameters

* **`type`**: Used to filter the type of the content to retrieve. When it's not specified, all contents of all types will be returned. These are the possible values: `show`, `series`, `season`, `episode`, `live_event`, `live_stream`, `on_demand_live`, `rider_clip` and `tv_channel`.You can specify many comma separated types.

 ***Examples***: `show,series`, `show,series,live_event`

* **`search`**: A text to search a contents by its name, description and metadata.

 ***Examples***: `event london`, `Daisy Dines`

* **`name`**: A text to filter contents by only the content name:

 ***Examples***: `event london`, `Daisy Dines`

* **`perPage`**: The maximum number of elements to get.

 ***Examples***: `10`, `20`

 * **`page`**: The page number to get. Here are some example values:

 ***Examples***: `1`, `4`

 * **`parent_id`**: The parent entry ID. It can be useful to get the season of an episode or the live event an on demand content belongs to.

 ***Examples***: `846`, `34754`

 * **`term`**: Used to filter the entries by term ID.

 ***Examples***: `20`, `5`

 * **`terms`**: In the same way as the `term` parameter, it accepts a term ID as a value, or many comma separated term IDs.

 ***Examples***: `20`, `20,5`

* **`tags`**: Allows to filter the contents by the tags assigned. This parameter accepts a single tag name or a set of comma separated tag names.

 ***Examples***: `british dressage`, `british dressage,uk-eventing`

* **`timeZone`**: Used to inform about the timezone of the user. When this parameter is present, the start and end dates of the contents will be localised for the users via the `timezone_start_date` and `timezone_end_date` attributes.

 ***Examples***: `Europe/London`, `UTC+03:00`, `03:00`

* **`order_by`**: Used to specify the field used to order the content. If this parameter is not specified, the contents will be ordered by cration date by default.

 ***Examples***: `created_at`, `start_date`, `name`

* **`order_direction`**: Allows alter the ascending or descending ordering of the results. The default value is `DESC` and the possible values are `ASC` and `DESC`. As an example:

 ***Examples***: `ASC`, `DESC`



#### Response Examples

* **Code 200** Success
 ```json
Array
(
    [
    0
] => 274162852
    [
    1
] => 258310772
    [
    2
] => 1_wll3007o
    [
    3
] => 280085972
    [
    4
] => 272162992
    [
    5
] => 279965472
    [
    6
] => 276947633
    [
    7
] => 279200482
    [
    8
] => 261319562
)
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

