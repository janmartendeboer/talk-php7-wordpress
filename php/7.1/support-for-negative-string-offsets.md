# Support for negative string offsets

Support for negative string offsets has been added to the string manipulation functions accepting offsets, as well as to string indexing with [] or {}. In such cases, a negative offset is interpreted as being an offset from the end of the string.

```php
<?php
var_dump("abcdef"[-2]);
var_dump(strpos("aabbcc", "b", -3));
```

The above example will output:

```
string (1) "e"
int(3)
```

Negative string and array offsets are now also supported in the simple variable parsing syntax inside of strings.

```php
<?php
$string = 'bar';
echo "The last character of '$string' is '$string[-1]'.\n";
```

The above example will output:

```
The last character of 'bar' is 'r'.
```
