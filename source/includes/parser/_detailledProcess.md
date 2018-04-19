## Detailled process

```php
<?php
use Weglot\Client\Client;
use Weglot\Parser\Parser;
use Weglot\Parser\ConfigProvider\ServerConfigProvider;

// Url to parse
$url = 'https://foo.bar/baz';

// Config with $_SERVER variables
$config = new ServerConfigProvider();

// Fetching url content
$content = '...';

// Client
$client = new Client(getenv('WG_API_KEY'));
$parser = new Parser($client, $config);

// Run the Parser
$translatedContent = $parser->translate($content, 'en', 'de');
```

How it works:

Once you hit the `translate` function, what the `Parser` does ? Let's explain all steps, step by step:

1. Receiving & setting both original & destination language.
2. Depending on your API version, you'll now pass into `ignoredNodes` formatter. Basically, `ignoredNodes` mode is skip some tags into translations by using HTML entities, like that, we would have less sentences sent to Weglot API.
3. After that, we're using a library called [`simple_html_dom`](https://github.com/weglot/simple_html_dom) (with some internal tweaks) to fetch all HTML content.
4. Then we check if there is blocks you don't want to be translated (through `$excludeBlocks` array that you can set in `Parser` construct). We fetch them all and add a property to make sure we won't translate them (you can find this property in `Parser::ATTRIBUTE_NO_TRANSLATE` constant)
5. d
6. e