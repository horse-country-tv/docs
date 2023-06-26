---
sidebar_position: 1
---

# Plans

## GET `/partners/plans`

The **GET** `/partners/plans` endpoint is used to retrieve the partner plans.

#### Headers

* **Accept**: `application/json`

#### Authorization

* **Bearer**: Format: `Bearer <PARTNER_TOKEN>`. The token is provided by H&C.

#### Response Examples

* **Code 200** Success

 **Request to**: `/partners/plans`

 ```json
{
    "success": true,
    "data": [
        {
            "id": 1,
            "name": "HC+ Ridely",
            "mname": "hc_ridely",
            "title": null,
            "stripe_product_id": "prod_O5reBExBkrJhHE",
            "active": 1,
            "created_at": "2023-06-26T16:18:03.000000Z",
            "updated_at": "2023-06-26T16:19:44.000000Z",
            "laravel_through_key": 1
        }
    ]
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
