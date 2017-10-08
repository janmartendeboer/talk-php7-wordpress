# Nullable types

Type declarations for parameters and return values can now be marked as nullable by prefixing the type name with a question mark. This signifies that as well as the specified type, NULL can be passed as an argument, or returned as a value, respectively.

```php
<?php
function testReturn(): ?string
{
    return 'elePHPant';
}

var_dump(testReturn());

function testReturn(): ?string
{
    return null;
}

var_dump(testReturn());

function test(?string $name)
{
    var_dump($name);
}

test('elePHPant');
test(null);
test();
```

The above example will output:

```
string(10) "elePHPant"
NULL
string(10) "elePHPant"
NULL
Uncaught Error: Too few arguments to function test(), 0 passed in...
```
