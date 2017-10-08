# CSPRNG functions

Two new functions have been added to generate cryptographically secure integers and strings in a cross platform way: random_bytes() and random_int().

## Random bytes

```php
<?php
$bytes = random_bytes(5);
var_dump(bin2hex($bytes));
```

The above example will output something similar to:

```
string(10) "385e33f741"
```

## Random int

```php
<?php
var_dump(random_int(100, 999));
var_dump(random_int(-1000, 0));
```

The above example will output something similar to:

```
int(248)
int(-898)
```
