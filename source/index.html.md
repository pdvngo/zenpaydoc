---
title: API Reference

toc_footers:
  - <a href='https://account.zodaka.com/signup'>Sign Up Now</a>
  - <a href='https://www.zodaka.com/'>Documentation Powered by Zodaka</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Zenpay API! You can use our API to access Zenpay API endpoints, which can get information on various things in our database.

<!-- ---------------------------------------------------------------------------------------------------------------- -->
<!-- ---------------------------------------------------------------------------------------------------------------- -->
<!-- ---------------------------------------------------------------------------------------------------------------- -->

# App Tokens

<!-- ---------------------------------------------------------------------------------------------------------------- -->
## Create App Token

> JSON structured:

```json
{
    "data": {
        "token": "8c85c8a4-7b9d-38fb-bb8e-65d304a3efb9",
        "application_id": "106388e0-04e2-11ea-9700-6d2a1ac9da4c",
        "created_at": "2019-11-12T03:23:46.527Z"
    }
}
```

This endpoint create an application token.

### HTTP Request

`POST http://localhost:3000/api/applications/<ID>/tokens`

### Headers

Key           | Value                
------------- | -------------------- 
Authorization | Bearer *`{{token}}`*
Content-Type  | application/json

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the application to create

<!-- ---------------------------------------------------------------------------------------------------------------- -->

## Get App Token

> JSON structured:

```json
{
    "data": [
        {
            "token": "8c85c8a4-7b9d-38fb-bb8e-65d304a3efb9",
            "application_id": "106388e0-04e2-11ea-9700-6d2a1ac9da4c",
            "created_at": "2019-11-12T03:23:46.527Z"
        }
    ]
}
```

This endpoint retrieves all tokens.

### HTTP Request

`GET http://localhost:3000/api/applications/<ID>/tokens`

### Headers

Key           | Value                
------------- | -------------------- 
Authorization | Bearer *`{{token}}`* 
Content-Type  | application/json     

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the application to retrieve all tokens.

<!-- ---------------------------------------------------------------------------------------------------------------- -->

## Delete App Token

> JSON structured:

```json
{
    "id": "106388e0-04e2-11ea-9700-6d2a1ac9da4c",
    "token": "8c85c8a4-7b9d-38fb-bb8e-65d304a3efb9"
}
```

This endpoint deletes a specific token.

### HTTP Request

`DELETE http://localhost:3000/api/applications/<ID>/tokens/<TOKEN>`

### Headers

Key           | Value                
------------- | -------------------- 
Authorization | Bearer *`{{token}}`*

### URL Parameters

Parameter | Description
--------- | -----------
TOKEN     | The token to delete.
ID        | The application ID of the token to delete.

<!-- ---------------------------------------------------------------------------------------------------------------- -->
<!-- ---------------------------------------------------------------------------------------------------------------- -->
<!-- ---------------------------------------------------------------------------------------------------------------- -->

