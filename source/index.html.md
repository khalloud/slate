---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript
  - php

toc_footers:
  - <a href='https://ackoo.app/developers'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Ackoo API! You can use our API to access the Ackoo platform and integrate with it.

We have language bindings in Shell, Ruby, Python, JavaScript, and PHP! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Authentication

> To authorize, use this code:

```ruby
require 'ackoo'

api = ackoo::APIClient.authorize!('XXXXXX')
```

```python
import ackoo

api = ackoo.authorize('XXXXXX')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: XXXXXX"
```

```javascript
const ackoo = require('ackoo');

let api = ackoo.authorize('XXXXXX');
```

> Make sure to replace `XXXXXX` with your API key.

Ackoo uses API keys to allow access to the API. You can register a new Ackoo API key at our [developer portal](http://www.ackoo.app/developers).

Ackoo expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: XXXXXX`

<aside class="notice">
You must replace <code>XXXXXX</code> with your personal API key.
</aside>

# Libraries

You can install our libraries from your package/library managers.

# Transactions

```ruby
require 'ackoo'

api = ackoo::APIClient.authorize!('XXXXXX')
api.ackoo.get
```

```python
import ackoo

api = ackoo.authorize('XXXXXX')
api.ackoo.get()
```

```shell
curl "http://ackoo.app/api/"
  -H "Authorization: XXXXXX"
```

```javascript
const ackoo = require('ackoo');

let api = ackoo.authorize('XXXXXX');
let ackoo = api.ackoo.get();
```

> The above command returns JSON structured like this:

```json
[
  {
     "id":1,
     "created at":"timestamp",
     "finalized at":"timestamp",
     "total value":700,
     "status":"open",
     "user id":"XXXXXXXX",
     "merchant id":"sdfdsssdd",
     "campaign id":"sfddfsd",
     "publisher id":"6sdf00sdfs",
     "publisher ref id":"7sdggfsdf",
     "new user":true,
     "session id":"234gggdsd32434",
     "ackoo token":"calisfdsdfsco",
     "currency":"usd",
     "products":[
        {
           "serial":1,
           "id":"xx",
           "name":"adsf",
           "sku":"dfdd",
           "ean-upc":"3233222",
           "categories":[
              "xxx",
              "xxx",
              "xxx"
           ],
           "description":"sdfsdfdsfdfs",
           "price":222,
           "qty":3,
           "attributes":{
              "size":"m",
              "color":"blue"
           },
           "segments":[
              "a",
              "b",
              "c"
           ]
        },
     ],
     "merchant order id":"XXXXXXXX",
     "merchant creation date":"timestamp",
     "payment creation date":"calico",
     "channel":"ios app",
     "event type":"purchase",
     "modified at":"XXXXXXXX",
     "link id":"223sfsddd"
  },
  {
     "id":2,
     "created at":"timestamp",
     "finalized at":"timestamp",
     "total value":600,
     "status":"open",
     "user id":"XXXXXXXX",
     "merchant id":"sdfdsssdd",
     "campaign id":"sfddfsd",
     "publisher id":"6sdfsdfs",
     "publisher ref id":"7sdfsdf",
     "new user":"XXXXXXXX",
     "session id":"23432434",
     "ackoo token":"calico",
     "currency":"usd",
     "products":[
        {
           "serial":1,
           "id":"xx",
           "name":"adsf",
           "sku":"dfdd",
           "ean-upc":"3233222",
           "categories":[
              "xxx",
              "xxx",
              "xxx"
           ],
           "description":"sdfsdfdsfdfs",
           "price":222,
           "qty":3,
           "attributes":{
              "size":"m",
              "color":"blue"
           },
           "segments":[
              "a",
              "b",
              "c"
           ]
        },
        {
           "serial":2,
           "id":"xx",
           "name":"adsf",
           "sku":"dfdd",
           "ean-upc":"3233222",
           "categories":[
              "xxx",
              "xxx",
              "xxx"
           ],
           "description":"sdfsdfdsfdfs",
           "price":222,
           "qty":2,
           "attributes":{
              "size":"m",
              "color":"blue"
           },
           "segments":[
              "a",
              "b",
              "c"
           ]
        }
     ],
     "merchant order id":"XXXXXXXX",
     "merchant creation date":"timestamp",
     "payment creation date":"calico",
     "channel":"ios app",
     "event type":"purchase",
     "modified at":"XXXXXXXX",
     "link id":"223sfsddd"
  }
]
```

This endpoint retrieves all transactions.

### HTTP Request

`GET http://example.com/api/ackoo`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
advanced details | false | If set to true, the result will include advanced details.
new_user | true | If set to false, the result will include all transactions.

<aside class="success">
Remember — a safe transaction is an authenticated one!
</aside>

## Get a Specific transaction

```ruby
require 'ackoo'

api = ackoo::APIClient.authorize!('XXXXXX')
api.ackoo.get(2)
```

```python
import ackoo

api = ackoo.authorize('XXXXXX')
api.ackoo.get(2)
```

```shell
curl "http://example.com/api/ackoo/2"
  -H "Authorization: XXXXXX"
```

```javascript
const ackoo = require('ackoo');

let api = ackoo.authorize('XXXXXX');
let max = api.ackoo.get(2);
```

> The above command returns JSON structured like this:

```json
{
   "id":2,
   "created at":"timestamp",
   "finalized at":"timestamp",
   "total value":600,
   "status":"open",
   "user id":"XXXXXXXX",
   "merchant id":"sdfdsssdd",
   "campaign id":"sfddfsd",
   "publisher id":"6sdfsdfs",
   "publisher ref id":"7sdfsdf",
   "new user":"XXXXXXXX",
   "session id":"23432434",
   "ackoo token":"calico",
   "currency":"usd",
   "products":[
      {
         "serial":1,
         "id":"xx",
         "name":"adsf",
         "sku":"dfdd",
         "ean-upc":"3233222",
         "categories":[
            "xxx",
            "xxx",
            "xxx"
         ],
         "description":"sdfsdfdsfdfs",
         "price":222,
         "qty":3,
         "attributes":{
            "size":"m",
            "color":"blue"
         },
         "segments":[
            "a",
            "b",
            "c"
         ]
      },
      {
         "serial":2,
         "id":"xx",
         "name":"adsf",
         "sku":"dfdd",
         "ean-upc":"3233222",
         "categories":[
            "xxx",
            "xxx",
            "xxx"
         ],
         "description":"sdfsdfdsfdfs",
         "price":222,
         "qty":2,
         "attributes":{
            "size":"m",
            "color":"blue"
         },
         "segments":[
            "a",
            "b",
            "c"
         ]
      }
   ],
   "merchant order id":"XXXXXXXX",
   "merchant creation date":"timestamp",
   "payment creation date":"calico",
   "channel":"ios app",
   "event type":"purchase",
   "modified at":"XXXXXXXX",
   "link id":"223sfsddd"
}
```

This endpoint retrieves a specific transaction.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/ackoo/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the transaction to retrieve

## Delete a Specific transaction

```ruby
require 'ackoo'

api = ackoo::APIClient.authorize!('XXXXXX')
api.ackoo.delete(2)
```

```python
import ackoo

api = ackoo.authorize('XXXXXX')
api.ackoo.delete(2)
```

```shell
curl "http://example.com/api/ackoo/2"
  -X DELETE
  -H "Authorization: XXXXXX"
```

```javascript
const ackoo = require('ackoo');

let api = ackoo.authorize('XXXXXX');
let max = api.ackoo.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific transaction.

### HTTP Request

`DELETE http://example.com/ackoo/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the transaction to delete
