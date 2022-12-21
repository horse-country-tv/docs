---
sidebar_position: 5
---

# Terms

## GET `/terms`

The **GET** `/terms` endpoint is used to retrieve the terms. For example, it can be useful when retrieving the terms of a specific taxonomy.

#### Headers

* **Accept**: `application/json`

#### Query Parameters

* **`taxonomy`**: Used to filter the taxonomy of the term. When it's not specified, all terms of all taxonomies will be returned.

 ***Examples***: `discipline`, `category`, `discipline,category`


* **`name`**: A text to filter contents by only the content name:

 ***Examples***: `dressage`, `eventing,dressage`

* **`perPage`**: The maximum number of elements to get.

 ***Examples***: `10`, `20`

 * **`page`**: The page number to get. Here are some example values:

 ***Examples***: `1`, `4`

* **`order_by`**: Used to specify the field used to order the content. If this parameter is not specified, the contents will be ordered by cration date by default.

 ***Examples***: `created_at`, `name`

* **`order_direction`**: Allows alter the ascending or descending ordering of the results. The default value is `DESC` and the possible values are `ASC` and `DESC`. As an example:

 ***Examples***: `ASC`, `DESC`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "collection": [
            {
                "id": 456,
                "kaltura_id": "255285613",
                "name": "The Ride: Race Across the Steppe",
                "taxonomy": "category",
                "created_at": "2022-11-12T01:27:51.000000Z",
                "updated_at": "2022-11-12T01:27:51.000000Z"
            },
            ...
        ],
        "meta": {
            "page": 1,
            "per_page": 20,
            "next_page": 2,
            "prev_page": false,
            "total_count": 436
        }
    }
}
 ```

## GET `/terms/{termId}`

The **GET** `/terms/{termId}` endpoint is used to retrieve a single term.

#### Route Parameters

* **termId**: The content ID to retrieve.

  ***Examples***: `2`, `200`

#### Response Examples


* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "id": 456,
        "kaltura_id": "255285613",
        "name": "The Ride: Race Across the Steppe",
        "taxonomy": "category",
        "created_at": "2022-11-12T01:27:51.000000Z",
        "updated_at": "2022-11-12T01:27:51.000000Z"
    }
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