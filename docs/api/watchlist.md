---
sidebar_position: 4
---

# Watchlist

## GET `/watchlist`

The **GET** `/watchlist` endpoint is used to retrieve the user watchlist contents.

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
                "id": 46,
                "user_id": 164,
                "content_id": 33968,
                "video_id": "1_xoism4wn",
                "created_at": "2022-12-20T23:29:26.000000Z",
                "updated_at": "2022-12-20T23:29:26.000000Z",
                "content": {
                    "id": 33968,
                    "parent_id": 33965,
                    "type": "episode",
                    "handler": "kaltura",
                    "handler_type": "media_entry",
                    "handler_id": "1_xoism4wn",
                    "name": "FIP World Polo Championships 2022",
                    "title": {
                        "en": "FIP World Polo Championships 2022"
                    },
                    "description": {
                        "en": "Highlights of the World Polo Championship final where the USA and Australia will contend for the highest honor in international polo competition."
                    },
                    "weight": 1,
                    "thumbnail": "https://cfvod.kaltura.com/p/1934501/sp/193450100/thumbnail/entry_id/1_xoism4wn/version/100001",
                    "thumbnail_handler": "kaltura",
                    "keywords": "",
                    "pricing": null,
                    "inplayer_asset_id": null,
                    "purchaseable": 0,
                    "start_date": "2022-11-21T15:27:00.000000Z",
                    "end_date": "2023-11-21T15:27:05.000000Z",
                    "countries_include": null,
                    "countries_exclude": null,
                    "created_at": "2022-11-21T15:23:46.000000Z",
                    "updated_at": "2022-12-09T13:58:42.000000Z",
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
                    "link": "http://dev.horseandcountry.localhost/series/280312722/episodes/1_xoism4wn",
                }
            },
            ...
        ],
        "meta": {
            "page": 1,
            "per_page": 20,
            "next_page": false,
            "prev_page": false,
            "total_pages": 1,
            "total_count": 9
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

## POST `/watchlist`

The **POST** `/watchlist` endpoint is used to add an element to the watchlist for the current authenticated user.

#### Headers

* **Format**: `application/json`
* **Accept**: `application/json`

#### Request Body Schema

* **`content_id`** *required*: The `id` of the content to be added to the watchlist.

#### Request Example

```json
{
    "content_id":  2014,
}
```
#### Response Examples

* **Code 201** Success
 ```json
{
    "success": true,
    "message ": "Resource correctly created"
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

## DELETE `/watchlist`

The **DELETE** `/watchlist` endpoint is used to delete all the contents added to the watchlist for the user who is currently logged in.

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

## DELETE `/watchlist/{elementId}`

The **DELETE** `/watchlist/{elementId}` endpoint is used to delete the specified element from the watchlist.

#### Authorization

* **Bearer**: You can get the bearer token using the `/login` endpoint. Format: `Bearer <TOKEN>`

#### Route Parameters

* **elementId**: The watchlist element ID.

  ***Examples***: `4`,`10`


#### Response Examples

* **Code 200** Success (with access)
 ```json
{
    "code": 200,
    "success": true,
    "message ": "Resource correctly deleted"
}
 ```

 * **Code 404** Failure (no watchlist element found)
 ```json
{
    "code": 404,
    "success": false,
    "message": "Watchlist element not found"
}
 ```

 * **Code 403** Forbidden (no access to the watchlist element)
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
