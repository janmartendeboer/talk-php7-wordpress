# Void functions

A void return type has been introduced. Functions declared with void as their return type must either omit their return statement altogether, or use an empty return statement. NULL is not a valid return value for a void function.

```php
<?php
function swap(&$left, &$right): void
{
    if ($left === $right) {
        return;
    }

    $tmp = $left;
    $left = $right;
    $right = $tmp;
}

$a = 1;
$b = 2;
var_dump(swap($a, $b), $a, $b);
```

The above example will output:

```
null
int(2)
int(1)
```

Attempting to use a void function's return value simply evaluates to NULL, with no warnings emitted. The reason for this is because warnings would implicate the use of generic higher order functions.
