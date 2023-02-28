---
sidebar_position: 1
---

# Authorization

## POST `/login`

The **POST** `/login` endpoint is used authenticate on the application, returning a Bearer token. This token should be included on the `Athorization` of the requests to the login protected endpoints. 

#### Headers

* **Format**: `application/json`
* **Accept**: `application/json`

#### Request Body Schema

* **`email`** *required*: The email of the user who is trying to authenticate.
* **`password`** *required*: The password of the user who is trying to authenticate.

#### Request Example

```json
{
    "email":  "example@domain.tld",
    "password": "example"
}
```

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "message": "User Logged In Successfully",
    "token": "9|AAGoXfjV72GYyXf7S3DkllA2lKTAGOFCastgnPpu"
}
 ```

* **Code 401** Failure
 ```json
{
    "success": false,
    "message": "The Email & Password provided do not match with our record."
}
 ```
 
## GET `/auth/user`

The **GET** `/auth/user` endpoint is used to return information about the user who is currently logged in.

#### Authorization

* **Bearer**: Format: `Bearer <TOKEN>`. You can get the bearer token using the `/login` endpoint.

#### Headers

* **Format**: `application/json`
* **Accept**: `application/json`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "code": 200,
    "data": {
        "id": 164,
        "name": "Test",
        "email": "test-annual-gold@horseandcountry.tv",
        "inplayer_id": "67587",
        "inplayer_uuid": "d7297f2d-0ca3-4e50-a273-6db4a36d87b5",
        "created_at": "2022-11-22T00:44:04.000000Z",
        "updated_at": "2022-11-22T17:01:34.000000Z",
        "last_login": null,
        "surname": "Gold",
        "full_name": "Test Gold"
    }
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "code": 401,
    "message": "Unauthenticated."
}
 ```

## POST `/auth/password/reset`

The **POST** `/auth/password/reset` endpoint is used to reset the password of the user with the specified email address.

#### Headers

* **Format**: `application/json`
* **Accept**: `application/json`

#### Request Body Schema

* **`email`** *required*: The email of the user.

#### Request Example

```json
{
    "email":  "example@domain.tld",
}
```

#### Response Examples

* **Code 200** Success. The user will get an email with the instructions to reset his password.
 ```json
{
    "success": true,
    "code": 200,
    "message ": "Password reset link has been sent to your email"
}
 ```

* **Code 400** Failure.
 ```json
{
    "success": false,
    "code": 400,
    "message ": "The customer with the given email address does not exists."
}
 ```

## GET `/auth/user/plans`

The **GET** `/auth/user/plans` endpoint is used to return the plans which the logged in user has access to.

#### Authorization

* **Bearer**: Format: `Bearer <TOKEN>`. You can get the bearer token using the `/login` endpoint.

#### Headers

* **Accept**: `application/json`

#### Query Parameters

* **`with`**: Used to get more details about the subscription. The only accepted value is `subscription`, and when present will also return the subscription detail of the user to the plan.

 ***Examples***: `subscription`

#### Response Examples

* **Code 200** Success
 ```json
{
    "success": true,
    "code": 200,
    "data": [
        {
            "user_id": 5568,
            "plan_id": "annual",
            "plan": {
                "name": "Annual",
                "inplayer_package_id": 107814,
                "currencies": {
                    "GBP": 26423,
                    "USD": 26425,
                    "AUD": 26426,
                    "EUR": 26427,
                    "SEK": 26428,
                    "CAD": 38033
                },
                "default": true,
                "active": true,
                "id": "annual"
            },
            "access": {
                "type": "purchased",
                "merchant_id": 50808,
                "customer_id": 67587,
                "consumer_email": "test@horseandcountry.tv",
                "item_id": 107814,
                "item_title": "H&C+ Annual",
                "item_access_id": 1520546,
                "starts_at": 1638540467,
                "created_at": "2023-02-26T23:09:20.000000Z",
                "expires_at": "2024-02-26T23:09:20.000000Z",
                "revoked": 0,
                "purchased_access_fee_id": 26423,
                "purchased_access_fee_description": "GBP",
                "purchased_access_fee_type": "subscription",
                "purchased_amount": 59.99,
                "purchased_currency": "GBP",
                "parent_resource_id": "Test-ST",
                "is_trial": false,
                "payment_method": "Card",
                "payment_tool": "visa 4242",
                "subscription": {
                    "cancel_token": "Test-ST",
                    "subscription_id": "Test-ST",
                    "description": "GBP",
                    "item_title": "H&C+ Annual",
                    "item_id": 107814,
                    "item_type": "package",
                    "formatted_amount": "£59.99",
                    "subscription_price": 59.99,
                    "access_fee_id": 26423,
                    "charged_amount": 59.99,
                    "currency": "GBP",
                    "merchant_id": 50808,
                    "action_type": "recurrent",
                    "created_at": 1677452959,
                    "voucher": "",
                    "updated_at": 1677452960000,
                    "next_rebill_date": 1708988957,
                    "consumer_email": "test@horseandcountry.tv",
                    "consumer_id": 67587,
                    "payment_method_name": "Card",
                    "access_type": {
                        "id": 20,
                        "name": "subscription",
                        "period": "year",
                        "quantity": 1
                    },
                    "expiry_date": 1708988959,
                    "is_monthly_free_trial": false,
                    "is_monthly_installment": false,
                    "is_annual": true,
                    "is_annual_gold": false,
                    "free_trial_period_end_date": "",
                    "is_free_trial_active": false,
                    "can_be_canceled": true,
                    "is_canceled": false
                }
            }
        },
    ]
}
 ```

* **Code 401** Unauthenticated
 ```json
{
    "success": false,
    "code": 401,
    "message": "Unauthenticated."
}
 ```