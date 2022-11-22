---
sidebar_position: 1
---

# Introduction

Welcome to the H&C documentation.

The H&C API follows the REST architectural style and uses standard HTTP response codes to indicate success requests (2xx) or API errors (4xx, 5xx). It uses the standard **POST**, **PUT**, **PATCH**, **GET**, and **DELETE** REST HTTP methods.

The requests are performed via the standard GET URL Query parameters. When sending POST, PUT or PATCH, a JSON body should be used.

## Environment

This is the base URL for the `dev` environment:

```
https://dev.horseandcountry.tv/api/
```

This is the base URL for the `production` environment:

```
https://horseandcountry.tv/api/
```

## Standards

The API responses will follo the next standards based on the expected results:

* **Value**: When the result is expected to cantain a single value, the next schema is followed as a rule:
    ```json
    {
        success: <true|false>,
        result: <RESULT>
    }
    ```
* **Resource**: When the result is expected to cantain a single object, the next schema is followed as a rule:
    ```json
    {
        success: <true|false>,
        data: {
            <OBJECT_DATA>
        }
    }
    ```
* **Collection**: When the result is expected to cantain a collection of objects, the next schema is followed as a rule:
    ```json
    {
        success: <true|false>,
        data: {
            collection: {
                {
                    <OBJECT_DATA>
                },
                ...
            },
            meta: {
                <META_DATA>
            }
        }
    }
    ```