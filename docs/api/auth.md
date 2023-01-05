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