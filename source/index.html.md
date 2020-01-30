---
title: The Trade API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript
  - csharp

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://www.thelittlecodingco.com'>The Little Coding Company</a>

includes:
  - errors

search: true
---

# The Trade API

Welcome to the The Trade API! You can use our API to securely access your customers. The Trade API makes integrating your systems as simple as possible. Connect once to The Trade API, and we handle the rest.

Your customers may use on-premise ERP systems such as SAP and Oracle, they may use cloud systems such as Xero and Dynamics, or they may use spreadsheets or other on-premise technologies. 

The Trade API in conjunction with Tradeploy cuts the cost of integrations and rapidly increases your path to scale.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Customer Functions

## Get All Entities
```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://thetradeapi.com/api/entities"
  -H "Authorization: bearer token"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
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

This endpoint retrieves all eligible invoices across all customers.

### HTTP Request

`GET http://thetradeapi.com/api/invoices`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Entity
```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://thetradeapi.com/api/entity/{entity}"
  -H "Authorization: bearer token"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
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

This endpoint retrieves all eligible invoices across all customers.

### HTTP Request

`GET http://thetradeapi.com/api/invoices`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>


# Trade Functions

## Get All Invoices

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://thetradeapi.com/api/invoices"
  -H "Authorization: bearer token"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
{
    "version": "1.0",
    "versionDate": "2019-01-01",
    "invoiceNumber": "INV001",
    "buyer": {
	"name": "bbbbbb",
	"entityUid": "224234",
	"registrationNumber": "324234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"active": 1,
		},
    "supplier": {
	"name": "ssssss",
	"entityUid": "324234",
	"registrationNumber": "324234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": null,
	"active": 1,
		},
    "obligor": {
	"name": "oooooo",
	"entityUid": "774234",
	"registrationNumber": "424234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"active": 1,
		},
    "issueDate": "2019-10-12",
    "dueDate": "2019-11-12",
    "amount": 12345.67,
    "currency": "GBP",
    "balanceDue": 5000,
    "amountPaid": 7000,
    "dilution": 345.67,
    "closeDate": "",
    "expectedSettlementDate": "2019-11-12",
    "purchaseOrder": "PO123",
    "purchaseOrderVersion": "1.0",
    "reference": "",
    "shipTo": {
	"line1": "address line 1",
	"line2": "address line 2",
	"townCity": "my town",
	"region": "county",
	"country": "UK",
	"postCode": "CV64RT",
		},
    "shipper": "hhhhhh",
    "trackingNumber": "tttttttt",
    "paymentMethod": "cash",
    "disputeAmount": 0,
    "tax": 0,
    "jurisdiction": "UK",
    "status": "issued",
    "invoiceId": ""
},
{
    "version": "1.0",
    "versionDate": "2019-01-01",
    "invoiceNumber": "INV001",
    "buyer": {
	"name": "bbbbbb",
	"entityUid": "224234",
	"registrationNumber": "324234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"active": 1,
		},
    "supplier": {
	"name": "ssssss",
	"entityUid": "324234",
	"registrationNumber": "324234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": null,
	"active": 1,
		},
    "obligor": {
	"name": "oooooo",
	"entityUid": "774234",
	"registrationNumber": "424234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"active": 1,
		},
    "issueDate": "2019-10-12",
    "dueDate": "2019-11-12",
    "amount": 12345.67,
    "currency": "GBP",
    "balanceDue": 5000,
    "amountPaid": 7000,
    "dilution": 345.67,
    "closeDate": "",
    "expectedSettlementDate": "2019-11-12",
    "purchaseOrder": "PO123",
    "purchaseOrderVersion": "1.0",
    "reference": "",
    "shipTo": {
	"line1": "address line 1",
	"line2": "address line 2",
	"townCity": "my town",
	"region": "county",
	"country": "UK",
	"postCode": "CV64RT",
		},
    "shipper": "hhhhhh",
    "trackingNumber": "tttttttt",
    "paymentMethod": "cash",
    "disputeAmount": 0,
    "tax": 0,
    "jurisdiction": "UK",
    "status": "issued",
    "invoiceId": ""
}
]
```

This endpoint retrieves all eligible invoices across all customers.

### HTTP Request

`GET http://thetradeapi.com/api/invoices`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Invoice

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://thetradeapi.com/api/invoice/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
    "version": "1.0",
    "versionDate": "2019-01-01",
    "invoiceNumber": "INV001",
    "buyer": {
	"name": "bbbbbb",
	"entityUid": "224234",
	"registrationNumber": "324234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"active": 1,
		},
    "supplier": {
	"name": "ssssss",
	"entityUid": "324234",
	"registrationNumber": "324234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": null,
	"active": 1,
		},
    "obligor": {
	"name": "oooooo",
	"entityUid": "774234",
	"registrationNumber": "424234",
	"legalAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"billingAddress": {
		"line1": "address line 1",
		"line2": "address line 2",
		"townCity": "my town",
		"region": "county",
		"country": "UK",
		"postCode": "CV64RT",
			},
	"active": 1,
		},
    "issueDate": "2019-10-12",
    "dueDate": "2019-11-12",
    "amount": 12345.67,
    "currency": "GBP",
    "balanceDue": 5000,
    "amountPaid": 7000,
    "dilution": 345.67,
    "closeDate": "",
    "expectedSettlementDate": "2019-11-12",
    "purchaseOrder": "PO123",
    "purchaseOrderVersion": "1.0",
    "reference": "",
    "shipTo": {
	"line1": "address line 1",
	"line2": "address line 2",
	"townCity": "my town",
	"region": "county",
	"country": "UK",
	"postCode": "CV64RT",
		},
    "shipper": "hhhhhh",
    "trackingNumber": "tttttttt",
    "paymentMethod": "cash",
    "disputeAmount": 0,
    "tax": 0,
    "jurisdiction": "UK",
    "status": "issued",
    "invoiceId": ""
}```

This endpoint retrieves a specific invoice.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://thetradeapi.com/invoices/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://thetradeapi.com/api/kittens/2"
  -X DELETE
  -H "Authorization: bearer token"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
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

`DELETE http://thetradeapi.com/invoice/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete

