## WordType

```php
<?php
use Weglot\Client\Api\Enum\WordType;

// You can find all theses values through WordType abstract class
$wordType = WordType::GENERIC;

// ...
```

Used to defined how a sentence gonna be used.

Short-name | Value | Description
--------- | -------- | -----------
GENERIC | 0 | ???
TEXT | 1 | ???
VALUE | 2 | ???
PLACEHOLDER | 3 | ???
META_CONTENT | 4 | ???
IFRAME_SRC | 5 | ???
IMG_SRC | 6 | ???
IMG_ALT | 7 | ???
PDF_HREF | 8 | ???