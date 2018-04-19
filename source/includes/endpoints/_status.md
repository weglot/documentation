## Status

```php
<?php
use Weglot\Client\Client;
use Weglot\Client\Endpoint\Status;

$client = new Client(getenv('WG_API_KEY'));
$status = new Status($client);
```

```shell
curl -I "https://api.weglot.com/status?api_key=my_api_key"
```

> The above command returns JSON structured like this:

```
HTTP/1.1 200 OK
```

This endpoint is used as check-alive. You can use it to check if Weglot API is up and running.

### HTTP Request

`GET https://api.weglot.com/status`

### Returned Content

The returned content is just a simple empty JSON array. The interesting part is to check if status code is `200`.

<aside class="notice">
There is no real "content" for this endpoint, you should only check <code>200</code> status-code.
</aside>

<aside class="warning">
This is only a check-alive endpoint, don't spam it.
</aside>