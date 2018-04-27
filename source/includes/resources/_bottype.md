## BotType

```php
<?php
use Weglot\Client\Api\Enum\BotType;

// You can find all theses values through BotType abstract class
$botType = BotType::HUMAN;

// ...
```

Used to defined how a sentence gonna be used.

Short-name | Value | Description
--------- | -------- | -----------
HUMAN | 0 | Sent from human
OTHER | 1 | Sent from unknown source
GOOGLE | 2 | Sent from Google
BING | 3 | Sent from Bing
YAHOO | 4 | Sent from Yahoo
BAIDU | 5 | Sent from Baidu
YANDEX | 6 | Sent from Yandex