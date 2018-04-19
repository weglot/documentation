# Authentication

> To authorize, use this code:

```php
<?php
use Weglot\Client\Client;

$client = new Client('my_api_key');
```

```shell
# With shell, you can just pass the correct parameter with each request
curl "https://api.weglot.com/status?api_key=my_api_key"
```

> Make sure to replace `my_api_key` with your Weglot API key.

Weglot uses API Keys to allow access to the API. You can register a new Weglot API Key at: [Register](https://dashboard.weglot.com/register).

Weglot expects for the API Key to be included in all API requests to the server in the URL as a parameter that looks like the following:

`https://api.weglot.com/endpoint?api_key=my_api_key`

<aside class="notice">
Make sure to replace <code>my_api_key</code> with your Weglot API key.
</aside>