## Config providers

```php
<?php
use Weglot\Parser\ConfigProvider\ServerConfigProvider;
use Weglot\Parser\ConfigProvider\ManualConfigProvider;
use Weglot\Client\Api\Enum\BotType;

// Url to parse
$url = 'https://foo.bar/baz';

// Manual Config
$config = new ManualConfigProvider($url, BotType::HUMAN);

// Config with $_SERVER variables
$config = new ServerConfigProvider();

// Change title behavior from automatic to manual
$config->setTitle('Some title');

// Change back title behavior to automatic
$config->setTitle(null);
```

Some of the parameters we usually need in a (Translate query)[#translate] are skipped with config providers, actually we have two of them availables:

- `ManualConfigProvider`, data is fetched from what you give to the provider.
- `ServerConfigProvider`, data is fetched inside of the `Parser` (through `loadFromServer()` function) from the `$_SERVER` variable. Be carefull, it won't work if your environment doesn't fill it.

In addition to both providers, we have two ways to set the `title` that we send to Weglot API.
On both provider construct function, you'll have a `$title` variable that is `null` by default.
If you let it with the default value, you'll be in automatic mode.

Like that, the `Parser` would seek title tag in the HTML page and use it as `title`.
If you set it manually, we'll just use what you've put as `title`.

<aside class="notice">
You still can change <code>title</code> from automatic to manual by using <code>setTitle</code> function on provider (and reverse, by setting it as <code>null</code>).
</aside>