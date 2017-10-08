# Return type declarations

PHP 7 adds support for return type declarations. Similarly to argument type declarations, return type declarations specify the type of the value that will be returned from a function. The same types are available for return type declarations as are available for argument type declarations.

```php
<?php

function arraysSum(array ...$arrays): array
{
    return array_map(function(array $array): int {
        return array_sum($array);
    }, $arrays);
}

print_r(arraysSum([1,2,3], [4,5,6], [7,8,9]));
```

The above example will output:

```
Array
(
    [0] => 6
    [1] => 15
    [2] => 24
)
```

Full documentation and examples of return type declarations can be found in the return type declarations. reference.

