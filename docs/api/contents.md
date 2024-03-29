---
sidebar_position: 2
---

# Contents

## GET `/contents`

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

* **`thumbnails`**: Used to specify the sizes of the thumbnails to retrieve in pixels. When specified, the `thumbnails` field will be added. You can specify many comma separated sizes.

 ***Examples***: `600`, `600,800`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "collection": [
            {
                "id": 33740,
                "parent_id": null,
                "type": "live_event",
                "handler": "kaltura",
                "handler_type": "category",
                "handler_id": "272113332",
                "name": "Equestrian in the Park 2022 Australia",
                "title": {
                    "en": "Equestrian in the Park 2022 Australia"
                },
                "description": {
                    "en": "Live stream from the Equestrian in the Park 2022, Australia."
                },
                "weight": null,
                "thumbnail": "https://cdnsecakmi.kaltura.com/p/1934501/thumbnail/entry_id/1_8qqnretk",
                "thumbnail_handler": "kaltura",
                "keywords": "",
                "pricing": null,
                "start_date": "2022-11-12T06:43:47.000000Z",
                "end_date": "2022-11-12T23:43:57.000000Z",
                "countries_include": null,
                "countries_exclude": null,
                "created_at": "2022-11-12T06:43:47.000000Z",
                "updated_at": "2022-11-15T14:53:56.000000Z",
                "link": "http://dev.horseandcountry.localhost/live/272113332",
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
            },
            ...
        ],
        "meta": {
            "page": 1,
            "per_page": 20,
            "next_page": 2,
            "prev_page": false,
            "total_count": 301
        }
    }
}
 ```

## GET `/contents/{contentId}`

The **GET** `/contents/{contentId}` endpoint is used to retrieve a single content. For example, it can be useful when showing a video or a stream.

#### Route Parameters

* **contentId**: The content ID to retrieve.

  ***Examples***: `2`, `2400`


#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "id": 26655,
        "parent_id": null,
        "type": "live_event",
        "handler": "kaltura",
        "handler_type": "category",
        "handler_id": "254448243",
        "name": "Osberton Horse Trials 2021",
        "title": {
            "en": "Osberton Horse Trials 2021"
        },
        "description": {
            "en": null
        },
        "weight": null,
        "thumbnail": "https://cdnsecakmi.kaltura.com/p/1934501/thumbnail/entry_id/1_89aad76h",
        "thumbnail_handler": "kaltura",
        "keywords": "",
        "pricing": null,
        "start_date": "2021-10-01T13:22:22.000000Z",
        "end_date": "2021-10-10T13:22:26.000000Z",
        "countries_include": null,
        "countries_exclude": null,
        "created_at": "2021-10-01T13:22:22.000000Z",
        "updated_at": "2022-10-18T00:49:36.000000Z",
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
    },
}
 ```

* **Code 404** Failure
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```

## GET `/contents/{contentId}/access`

The **GET** `/contents/{contentId}/access` endpoint is used to retrieve the user access to a specific content and user.

#### Authorization

* **Bearer**: You can get the bearer token using the `/login` endpoint. Format: `Bearer <TOKEN>`

#### Route Parameters

* **contentId**: The content ID.

  ***Examples***: `2`, `33192`


#### Response Examples

* **Code 200** Success (with access)
 ```json
    {
        "code": 200,
        "success": true,
        "result": true
    }
 ```

 * **Code 402** Success (with no access)
 ```json
    {
        "code": 402,
        "success": true,
        "result": false
    }
 ```

* **Code 404** Failure (no content found)
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```

## GET `/contents/{contentId}/streams`

The **GET** `/contents/{contentId}/streams` endpoint is used to retrieve the stream sources for video contents. It's available for videos, shows, episosodes, on demand live contents, rider clips, tv channels and live streams. An access check will be performed using the Bearer token, and the streams will not be retrieved if a user do not have access to the content specified via the `contentId` route parameter.

#### Authorization

* **Bearer**: You can get the bearer token using the `/login` endpoint. Format: `Bearer <TOKEN>`

#### Route Parameters

* **contentId**: The content ID.

  ***Examples***: `2`, `33192`


#### Response Examples

* **Code 200** Success (with access)
 ```json
    {
        "code": 200,
        "success": true,
        "data": [
            {
                "width": 1920,
                "height": 1080,
                "bitrate": 4128,
                "frameRate": 29.97,
                "codec": "avc1",
                "extension": "mp4",
                "link": "https://cfvod.kaltura.com/pd/p/1934501/sp/193450100/serveFlavor/entryId/1_1q65gupg/v/1/flavorId/1_5q1anw44/fileName/Cross_Country_Highlights_of_the_Top_5_from_the_CIC3*_(HD_1080_-_WEB_(H264_4000)).mp4/name/a.mp4",
                "default": 1
            },
            ...
        ]
    }
 ```

 * **Code 402** Success (with no access)
 ```json
    {
        "code": 402,
        "success": false,
        "message ": "Forbidden access"
    }
 ```

* **Code 404** Failure (no content found)
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```

 
## GET `/contents/{contentId}/m3u8`

The **GET** `/contents/{contentId}/m3u8` endpoint is used to get the m3u8 HLS file. It's available for videos, shows, episosodes, on demand live contents, rider clips, tv channels and live streams. An access check will be performed using the Bearer token, and the file will not be retrieved if a user does not have access to the content specified via the `contentId` route parameter.

#### Authorization

* **Bearer**: You can get the bearer token using the `/login` endpoint. Format: `Bearer <TOKEN>`

#### Route Parameters

* **contentId**: The content ID.

  ***Examples***: `2`, `36425`


#### Response Examples

* **Code 200** Success (with access)
 ```json
    {
        "code": 200,
        "success": true,
        "data": "https://cfvod.kaltura.com/p/1934501/sp/0/playManifest/entryId/1_pbuxf6w9/format/applehttp/protocol/https/flavorParamId/301971/video.m3u8"
    }
 ```

 * **Code 402** Success (with no access)
 ```json
    {
        "code": 402,
        "success": false,
        "message ": "Forbidden access"
    }
 ```

* **Code 404** Failure (no content found)
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```


## GET `/contents/{contentId}/qr`

The **GET** `/contents/{contentId}/qr` endpoint is used to get the m3u8 HLS file. It's available for shows, series, seasons, episodes, live events, on demand live contents, tv channels and live streams.

#### Route Parameters

* **contentId**: The content ID.

  ***Examples***: `33543`


#### Response Examples

* **Code 200** Success (with access)
 ```json
    {
        "code": 200,
        "success": true,
        "result":"https:\/\/dev.horseandcountry.tv\/storage\/qr\/contents\/33543.png"
    }
 ```

* **Code 404** Failure (no content found)
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```