# Scalar type declarations

Scalar type declarations come in two flavours: coercive (default) and strict. The following types for parameters can now be enforced (either coercively or strictly): strings (string), integers (int), floating-point numbers (float), and booleans (bool). They augment the other types introduced in PHP 5: class names, interfaces, array and callable.

```php
<?php
// Coercive mode
function sumOfInts(int ...$ints)
{
    return array_sum($ints);
}

var_dump(sumOfInts(2, '3', 4.1));
```

The above example will output:

```
int(9)
```

To enable strict mode, a single declare directive must be placed at the top of the file. This means that the strictness of typing for scalars is configured on a per-file basis. This directive not only affects the type declarations of parameters, but also a function's return type (see return type declarations, built-in PHP functions, and functions from loaded extensions.

Full documentation and examples of scalar type declarations can be found in the type declaration reference.
