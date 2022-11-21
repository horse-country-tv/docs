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