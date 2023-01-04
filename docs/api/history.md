---
sidebar_position: 5
---


# History

## GET `/history`

The **GET** `/history` endpoint is used to retrieve the user history for the logged in user. The referenced contents will be included with the retrieved history elements.

#### Authorization

* **Bearer**: Format: `Bearer <TOKEN>`. You can get the bearer token using the `/login` endpoint.

#### Headers

* **Accept**: `application/json`

#### Query Parameters

* **`perPage`**: The maximum number of elements to get.

 ***Examples***: `10`, `20`

 * **`page`**: The page number to get. Here are some example values:

 ***Examples***: `1`, `4`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "collection": [
            {
                "_id": "63b58589d495699876030f42",
                "content": {
                    "id": 760,
                    "parent_id": 32753,
                    "type": "episode",
                    "handler": "kaltura",
                    "handler_type": "media_entry",
                    "handler_id": "1_52lvmc4z",
                    "name": "Cross Country Highlights of the Top 5 from the CIC2*",
                    "title": {
                        "en": "Cross Country Highlights of the Top 5 from the CIC2*"
                    },
                    "description": {
                        "en": "Cross Country Highlights of the Top 5 from the CIC2*"
                    },
                    "weight": null,
                    "thumbnail": "https://cfvod.kaltura.com/p/1934501/sp/193450100/thumbnail/entry_id/1_52lvmc4z/version/100001",
                    "thumbnail_handler": "kaltura",
                    "keywords": "",
                    "pricing": null,
                    "inplayer_asset_id": null,
                    "purchaseable": 0,
                    "start_date": "2017-03-20T19:28:19.000000Z",
                    "end_date": null,
                    "countries_include": null,
                    "countries_exclude": null,
                    "created_at": "2017-03-26T13:38:47.000000Z",
                    "updated_at": "2022-11-30T04:14:22.000000Z",
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
                    },
                    "link": "https://dev.horseandcountry.tv/series/263552782/episodes/1_52lvmc4z"
                },
                "user_id": 6933,
                "content_id": 760,
                "time": 10,
                "percentage": 60,
                "updated_at": "2023-01-04T13:56:25.652000Z",
                "created_at": "2023-01-04T13:56:25.652000Z"
            }
            ...
        ],
        "meta": {
            "page": 1,
            "per_page": 20,
            "next_page": false,
            "prev_page": false,
            "total_pages": 2,
            "total_count": 25
        }
    }
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated."
}
 ```

 
## GET `/watchlist/{watchedVideoId}`

The **GET** `/watchlist/{watchedVideoId}` endpoint is used to retrieve a single watched element from the history.

#### Authorization

* **Bearer**: Format: `Bearer <TOKEN>`. You can get the bearer token using the `/login` endpoint.

#### Route Parameters

* **watchedVideoId**: The history element ID.

  ***Examples***: `63b58589d495699876030f42`,`63b58589d495699876030f43`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "_id": "63b58589d495699876030f42",
        "content": {
            "id": 760,
            "parent_id": 32753,
            "type": "episode",
            "handler": "kaltura",
            "handler_type": "media_entry",
            "handler_id": "1_52lvmc4z",
            "name": "Cross Country Highlights of the Top 5 from the CIC2*",
            "title": {
                "en": "Cross Country Highlights of the Top 5 from the CIC2*"
            },
            "description": {
                "en": "Cross Country Highlights of the Top 5 from the CIC2*"
            },
            "weight": null,
            "thumbnail": "https://cfvod.kaltura.com/p/1934501/sp/193450100/thumbnail/entry_id/1_52lvmc4z/version/100001",
            "thumbnail_handler": "kaltura",
            "keywords": "",
            "pricing": null,
            "inplayer_asset_id": null,
            "purchaseable": 0,
            "start_date": "2017-03-20T19:28:19.000000Z",
            "end_date": null,
            "countries_include": null,
            "countries_exclude": null,
            "created_at": "2017-03-26T13:38:47.000000Z",
            "updated_at": "2022-11-30T04:14:22.000000Z",
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
            },
            "link": "https://dev.horseandcountry.tv/series/263552782/episodes/1_52lvmc4z"
        },
        "user_id": 6933,
        "content_id": 760,
        "time": 10,
        "percentage": 60,
        "updated_at": "2023-01-04T13:56:25.652000Z",
        "created_at": "2023-01-04T13:56:25.652000Z"
    }
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated."
}
 ```

* **Code 404** Failure (no history element found)
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```

 * **Code 403** Forbidden (no access to the history element)
 ```json
    {
        "code": 403,
        "success": false,
        "message": "Forbidden"
    }
 ```

## POST `/history`

The **POST** `/history` endpoint is used to add an element to the history for the current authenticated user.

#### Authorization

* **Bearer**: Format: `Bearer <TOKEN>`. You can get the bearer token using the `/login` endpoint.

#### Headers

* **Format**: `application/json`
* **Accept**: `application/json`

#### Request Body Schema

* **`content_id`** *required*: The `id` of the content to be added to the history.
* **`time`**: The time watched for the video, so it's possible to continue watching it.
* **`percentage`**: The percentage watched of the video.

#### Request Example

```json
{
    "content_id": 760,
    "time": 10,
    "percentage": 60
}
```
#### Response Examples

* **Code 201** Success
 ```json
{
    "success": true,
    "message ": "Resource correctly created",
    "code": 201
}
 ```

* **Code 400** Content ID missing
 ```json
{
    "code": 400,
    "success": false,
    "message": "'The content ID was not provided"
}
 ```

* **Code 400** Content not found
 ```json
{
    "code": 404,
    "success": false,
    "message": "'The content was not found"
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated."
}
 ```

## PUT `/history/{watchedVideoId}`

The **PUT** `/history/{watchedVideoId}` endpoint is used to update an element from the history for the current authenticated user.

#### Authorization

* **Bearer**: Format: `Bearer <TOKEN>`. You can get the bearer token using the `/login` endpoint.

#### Headers

* **Format**: `application/json`
* **Accept**: `application/json`

#### Route Parameters

* **watchedVideoId**: The history element ID.

  ***Examples***: `63b58589d495699876030f42`,`63b58589d495699876030f43`

#### Request Body Schema

* **`time`**: The time watched for the video, so it's possible to continue watching it.
* **`percentage`**: The percentage watched of the video.

#### Request Example

```json
{
    "time": 10,
    "percentage": 60
}
```
#### Response Examples

* **Code 200 ** Success
 ```json
{
    "success": true,
    "message ": "Resource correctly updated",
    "code": 200
}
 ```

 * **Code 403** Forbidden (no access to the history element)
 ```json
    {
        "code": 403,
        "success": false,
        "message": "Forbidden"
    }
 ```

* **Code 400** Content not found
 ```json
{
    "code": 404,
    "success": false,
    "message": "The resource was not found"
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated."
}
 ```

## DELETE `/history`

The **DELETE** `/watchlist` endpoint is used to delete all the contents added to the history for the user who is currently logged in.

#### Authorization

* **Bearer**: You can get the bearer token using the `/login` endpoint. Format: `Bearer <TOKEN>`

#### Response Examples

* **Code 200** Success (with access)
 ```json
{
    "code": 200,
    "success": true,
    "message ": "Resources correctly deleted"
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated."
}
 ```

## DELETE `/history/{watchedVideoId}`

The **DELETE** `/history/{watchedVideoId}` endpoint is used to delete the specified element from the history.

#### Authorization

* **Bearer**: You can get the bearer token using the `/login` endpoint. Format: `Bearer <TOKEN>`

#### Route Parameters

* **watchedVideoId**: The watchlist element ID.

  ***Examples***: `63b58589d495699876030f42`,`63b58589d495699876030f43`


#### Response Examples

* **Code 200** Success (with access)
 ```json
{
    "code": 200,
    "success": true,
    "message ": "Resource correctly deleted"
}
 ```

 * **Code 404** Failure (no history element found)
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```

 * **Code 403** Forbidden (no access to the history element)
 ```json
    {
        "code": 403,
        "success": false,
        "message": "Forbidden"
    }
 ```
 
* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated."
}
 ```







 