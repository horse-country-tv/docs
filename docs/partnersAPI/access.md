---
sidebar_position: 1
---

# Accesses

## GET `/partners/accesses`

The **GET** `/partners/accesses` endpoint is used to retrieve the access information for the plans connected with the partner.

#### Headers

* **Accept**: `application/json`

#### Authorization

* **Bearer**: Format: `Bearer <PARTNER_TOKEN>`. The token is provided by H&C.

#### Query Parameters

* **`perPage`**: The maximum number of elements to get.

 ***Examples***: `10`, `20`

 * **`page`**: The page number to get. Here are some example values:

  ***Examples***: `1`, `4`

* **`with`**: Allows to get the relations of the access. One or more comma separated values can be specified. These are the possible values: `user` and `subscribable`. You can specify many comma separated values.

 ***Examples***: `user`, `user,subscribable`

#### Response Examples

* **Code 200** Success

 **Request to**: `/partners/accesses`

 ```json
{
    "success": true,
    "data": {
        "collection": [
            {
                "id": 1,
                "user_id": 7468,
                "handler": "cashier",
                "handler_id": "1",
                "subscribable_type": "plan",
                "subscribable_id": 1,
                "status": "active",
                "order_row_id": null,
                "trial_expires_at": null,
                "expires_at": null,
                "created_at": "2023-06-26T18:35:16.000000Z",
                "updated_at": "2023-06-26T18:35:18.000000Z"
            },
            {
                "id": 2,
                "user_id": 7452,
                "handler": "cashier",
                "handler_id": "2",
                "subscribable_type": "plan",
                "subscribable_id": 1,
                "status": "active",
                "order_row_id": null,
                "trial_expires_at": null,
                "expires_at": null,
                "created_at": "2023-06-26T20:19:21.000000Z",
                "updated_at": "2023-06-26T20:19:23.000000Z"
            }
        ],
        "meta": {
            "page": 1,
            "per_page": 20,
            "next_page": false,
            "prev_page": false,
            "total_pages": 1,
            "total_count": 2
        }
    }
}
 ```

 **Request to**: `/partners/accesses?with=user,subscribable&page=1&perPage20`

 ```json
 {
    "success": true,
    "data": {
        "collection": [
            {
                "id": 1,
                "user_id": 7468,
                "handler": "cashier",
                "handler_id": "1",
                "subscribable_type": "plan",
                "subscribable_id": 1,
                "status": "active",
                "order_row_id": null,
                "trial_expires_at": null,
                "expires_at": null,
                "created_at": "2023-06-26T18:35:16.000000Z",
                "updated_at": "2023-06-26T18:35:18.000000Z",
                "user": {
                    "id": 7468,
                    "name": "Edu ",
                    "email": "eduardol+4015@horseandcountry.tv",
                    "email_verified_at": null,
                    "date_of_birth": null,
                    "country": null,
                    "postcode": null,
                    "region": null,
                    "city": null,
                    "marketing": 0,
                    "current_team_id": null,
                    "inplayer_id": "82169",
                    "created_at": "2023-06-22T21:56:33.000000Z",
                    "updated_at": "2023-06-26T18:35:14.000000Z",
                    "preferences": null,
                    "last_login": "2023-06-26 14:42:25",
                    "used_free_trial": 0,
                    "trial_ends_at": null,
                    "full_name": "Edu ",
                    "short_name": "Edu ."
                },
                "subscribable": {
                    "id": 1,
                    "name": "HC+ Ridely",
                    "mname": "hc_ridely",
                    "title": null,
                    "stripe_product_id": "prod_O5reBExBkrJhHE",
                    "active": 1,
                    "created_at": "2023-06-26T16:18:03.000000Z",
                    "updated_at": "2023-06-26T16:19:44.000000Z"
                }
            },
            {
                "id": 2,
                "user_id": 7452,
                "handler": "cashier",
                "handler_id": "2",
                "subscribable_type": "plan",
                "subscribable_id": 1,
                "status": "active",
                "order_row_id": null,
                "trial_expires_at": null,
                "expires_at": null,
                "created_at": "2023-06-26T20:19:21.000000Z",
                "updated_at": "2023-06-26T20:19:23.000000Z",
                "user": {
                    "id": 7452,
                    "name": "Test Test",
                    "email": "eduardol@horseandcountry.tv",
                    "email_verified_at": null,
                    "date_of_birth": null,
                    "country": null,
                    "postcode": null,
                    "region": null,
                    "city": null,
                    "marketing": 0,
                    "current_team_id": null,
                    "inplayer_id": "74728",
                    "created_at": "2023-02-27T19:17:07.000000Z",
                    "updated_at": "2023-06-26T20:19:18.000000Z",
                    "preferences": null,
                    "last_login": "2023-06-26 19:59:23",
                    "used_free_trial": 0,
                    "trial_ends_at": null,
                    "full_name": "Test Test",
                    "short_name": "Test T."
                },
                "subscribable": {
                    "id": 1,
                    "name": "HC+ Ridely",
                    "mname": "hc_ridely",
                    "title": null,
                    "stripe_product_id": "prod_O5reBExBkrJhHE",
                    "active": 1,
                    "created_at": "2023-06-26T16:18:03.000000Z",
                    "updated_at": "2023-06-26T16:19:44.000000Z"
                }
            }
        ],
        "meta": {
            "page": "1",
            "per_page": 20,
            "next_page": false,
            "prev_page": false,
            "total_pages": 1,
            "total_count": 2
        }
    }
 }
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated.",
    "code": 401
}
 ```


## GET `/accesses/{accessId}`

The **GET** `/accesses/{accessId}` endpoint is used to retrieve a single access.

#### Route Parameters

* **accessId**: The access ID to retrieve.

  ***Examples***: `2`, `1`

#### Query Parameters

* **`with`**: Allows to get the relations of the access. One or more comma separated values can be specified. These are the possible values: `user` and `subscribable`. You can specify many comma separated values.

#### Response Examples

**Request to**: `/partners/accesses/1`

* **Code 200** Success
 ```json
{
    "success": true,
    "data": {
        "id": 2,
        "user_id": 7452,
        "handler": "cashier",
        "handler_id": "2",
        "subscribable_type": "plan",
        "subscribable_id": 1,
        "status": "active",
        "order_row_id": null,
        "trial_expires_at": null,
        "expires_at": null,
        "created_at": "2023-06-26T20:19:21.000000Z",
        "updated_at": "2023-06-26T20:19:23.000000Z",
        "subscribable": {
            "id": 1,
            "name": "HC+ Ridely",
            "mname": "hc_ridely",
            "title": null,
            "stripe_product_id": "prod_O5reBExBkrJhHE",
            "active": 1,
            "created_at": "2023-06-26T16:18:03.000000Z",
            "updated_at": "2023-06-26T16:19:44.000000Z"
        }
    }
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "message": "Unauthenticated.",
    "code": 401
}
 ```

* **Code 404** Not found
 ```json
{
    "code": 404,
    "success": false,
    "message": "Resource not found"
}
 ```

 * **Code 404** Failure
 ```json
{
    "code": 402,
    "success": false,
    "message": "Forbidden access"
}
 ```
