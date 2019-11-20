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

Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/lord/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

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

Key           | Value                | Description
------------- | -------------------- | -------------------------------------------------------------------------------
Authorization | Bearer **`token`**   | 
Content-Type  | application/json     | 

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

# Kittens

## Get All Kittens

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

