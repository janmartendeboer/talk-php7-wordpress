# Trailing commas in list syntax

Only part of the RFC was accepted.

## Function/method arguments (declarations & calls)

```php
<?php
// Function/method arguments (call)
fooCall(
    $arg1,
    $arg2,
    $arg3,
);
 
// Function/method arguments (declaration)
function something(
    FooBarBazInterface $in,
    FooBarBazInterface $out,
) : bool {
}
```

# Grouped namespaces

```php
<?php
use Foo\Bar\{
    Foo,
    Bar,
    Baz,
};
```
