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

// setting expire
$client->getCache()->setExpire(86400);
```

For PHP, we're following [PSR-6](https://www.php-fig.org/psr/psr-6/) standard about caching.

Basically it can plug to any caching provider as long as you've [PSR-6](https://www.php-fig.org/psr/psr-6/) adaptor.
You can find [many of theses adaptors in this list](http://www.php-cache.com/en/latest/).

You'll find an example for a Redis server with Predis library on right pane.

### Expire

When you use cache we set an expire timer on every items.
By default, this timer is set to 604800 seconds but you can change it anytime you want by using `setExpire(int $seconds)` method.

### Granularity

The cache has changed a bit since its first version.
Originally we used to put the whole request into cache and use cache params to generate an unique ID.
We removed that behavior to focus on more specific caching for each Endpoints.
For example, on Translate endpoint, we're now caching each words to make sure our request (if there is one) is small as possible.