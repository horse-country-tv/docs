---
sidebar_position: 1
---

# Authorization

## POST `/login`

The **POST** `/auth/login` endpoint is used authenticate on the application, returning a Bearer token. This token should be included on the `Athorization` of the requests to the login protected endpoints. 

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