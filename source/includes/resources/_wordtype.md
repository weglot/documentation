## WordType

```php
<?php
use Weglot\Client\Api\Enum\WordType;

// You can find all theses values through WordType abstract class
$wordType = WordType::TEXT;

// ...
```

Used to defined how a sentence gonna be used.

Short-name | Value | Description
--------- | -------- | -----------
OTHER | 0 | Word is any of the above elements
TEXT | 1 | Word is simple text (default)
VALUE | 2 | Word is an attribute value
PLACEHOLDER | 3 | Word is a placeholder
META_CONTENT | 4 | Word is from meta content header
IFRAME_SRC | 5 | Word is an iframe source link
IMG_SRC | 6 | Word is an image source link
IMG_ALT | 7 | Word is an image alternative description
PDF_HREF | 8 | Word is a PDF source link