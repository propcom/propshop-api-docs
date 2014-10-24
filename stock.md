# Set Stock Overview

This API allows a third-party to set the stock for a particular product. There are two end-points for this, one to set stock for a single item and one for batch stock changes on multiple items. 

Both endpoints follow a similar format to each other and expect a JSON array in a POST request.

Your `api_key` is required for these endpoints to work successfully so make sure you have entered it in corectly when building your JSON array.

When Posting to the `Single Item Stock Update` endpoint the details of the item you are updating is contained within an array called `item` and for the `Batch Items Stock Update` endpoint you will have multiple items in an array called `items`.

An item requires the following fields:

* Either product SKU or ID (`sku` or `id`)
* Stock location ID (`location_id`)
* Stock level to set to (`level`)

# Endpoint Example Requests

## Example Single Item Stock Update

URL: `DOMAIN/admin/stock/api/set_stock.json`
Content-Type: `application/json`
Method: `POST`

Example:

```json
{ 
	"api_key" : "API_KEY_FOR_USER",
	"item" :
	{
		"sku" : "123456",
		"location_id" : 2,
		"level" : 5
	}
}
```

## Example Batch Items Stock Update

URL: `DOMAIN/admin/stock/api/set_stock_batch.json`
Content-Type: `application/json`
Method: `POST`

Example:

```json
{ 
	"api_key" : "API_KEY_FOR_USER",
	"items" :
	[
		{
			"sku" : "123456",
			"location_id" : 2,
			"level" : 5
		},
		{
			"id" : "654321",
			"location_id" : 2,
			"level" : 5
		},
	]
}
```
