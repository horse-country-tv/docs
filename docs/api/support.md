---
sidebar_position: 8
---

# Support

## GET `/support/context/{contextName?}/texts`

This endpoint will retrieve the text strings for the specified context, organized by language code.

#### Headers

* **Accept**: `application/json`

#### Route Parameters

* **`contextName`**: This parameter is used to specify the context name.

 ***Examples***: `comcast`

#### Response Examples

* **Code 200** Success
 ```json
{
  "success": true,
  "data": {
    "de": {
        "castingLoadingMessage":"Auf Abspielgerät laden",
        "getSocialNotYetSubscribedText":"Not yet Subscribed"
        ...
    },
    "en": {
        "castingLoadingMessage":"Loading on casting device",
        "getSocialNotYetSubscribedText":"Not yet Subscribed"
        ...
    }
    ...
  }
}
 ```
