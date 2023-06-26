---
sidebar_position: 6
---

# Rails

## GET `/rail-collections`

The **GET** `/rail-collections` endpoint will retrieve all rail collections. Each collection is composed of a set of rail endpoints. Those endpoints allow to get the contents for each rail in the collection.

#### Headers

* **Accept**: `application/json`

#### Query Parameters

* **`with`**: Allows to get the relations of the rail collections. One or more comma separated values can be specified.

 ***Examples***: `rails`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "collection": [
            {
                "id":17,
                "name":"Show Rail",
                "mname":"show_rail",
                "endpoint":"https:\/\/horseandcountry.tv\/api\/contents?type=shows",
                "created_at":"2022-12-14T02:10:02.000000Z",
                "updated_at":"2022-12-14T02:10:02.000000Z",
                "laravel_through_key":4
            },
            {
                "id":18,
                "name":"Series Rail",
                "mname":"series_rail",
                "endpoint":"https:\/\/horseandcountry.tv\/api\/contents?type=series",
                "created_at":"2022-12-14T02:10:12.000000Z",
                "updated_at":"2022-12-14T02:10:12.000000Z",
                "laravel_through_key":4
            },
            ...
        ],
        "meta": {
            "page": 1,
            "per_page": 20,
            "next_page": false,
            "prev_page": false,
            "total_pages": 1,
            "total_count": 4
        }
    }
}
 ```
