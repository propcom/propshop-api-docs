# Set Stock
This API allows a third-party to set the stock for a particular product.  There are two end-points for this, one for a single item and one for batch operations, both follow a similar format and expect a POST parameter.

As well as the `api_key` it also expects either an `item` array (for single) or `items` (for batch) each of which need:

* Either product SKU or ID (`sku` or `id`)
* Stock location ID (`location_id`)
* Stock level to set to (`level`)

## URLs
* Single: `DOMAIN/admin/stock/api/set_stock.json`
* Batch: `DOMAIN/admin/stock/api/set_stock_batch.json`

## Example Single Item Update
Updating a single items stock would expect the POST to be something like (note array key is `item`):

```php
'api_key'	=> API_KEY_FOR_USER,
'item'		=> array(
	'sku'			=> 123456,
	'location_id'		=> 2,
	'level'			=> 5
)
```

## Example Batch Item Update
Updating a multiple items stock would expect the POST to be something like (note array key is `items`):

```php
'api_key'	=> API_KEY_FOR_USER,
'items'		=> array(
	0 => array(
		'sku'			=> 123456,
		'location_id'		=> 2,
		'level'			=> 5
	),
	1 => array(
		'id'			=> 126,
		'location_id'		=> 2,
		'level'			=> 5
	)
)
```
