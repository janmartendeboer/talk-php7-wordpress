# IntlChar

The new IntlChar class seeks to expose additional ICU functionality. The class itself defines a number of static methods and constants that can be used to manipulate unicode characters.

```php
<?php
printf('%x', IntlChar::CODEPOINT_MAX);
echo IntlChar::charName('@');
var_dump(IntlChar::ispunct('!'));
```

The above example will output:

```
10ffff
COMMERCIAL AT
bool(true)
```

In order to use this class, the Intl extension must be installed.
