# Caching

Depending on library implementation we added caching to requests that we send to Weglot API.

## PHP

```php
<?php
// Redis init
$redis = new Redis([
    'scheme' => getenv('REDIS_SCHEME'),
    'host'   => getenv('REDIS_HOST'),
    'port'   => getenv('REDIS_PORT'),
]);
$redisPool = new PredisCachePool($redis);

// Client
$client = new Client(getenv('WG_API_KEY'));
$client->setCacheItemPool($redisPool);
```

For PHP, we're following [PSR-6](https://www.php-fig.org/psr/psr-6/) standard about caching.

Basically it can plug to any caching provider as long as you've [PSR-6](https://www.php-fig.org/psr/psr-6/) adaptor.
You can find (many of theses adaptors in this list](http://www.php-cache.com/en/latest/).

You'll find an example for a Redis server with Predis library on right pane.