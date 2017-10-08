# Generator delegation

Generators can now delegate to another generator, Traversable object or array automatically, without needing to write boilerplate in the outermost generator by using the yield from construct.

```php
<?php
function gen()
{
    yield 1;
    yield 2;
    yield from gen2();
}

function gen2()
{
    yield 3;
    yield 4;
}

foreach (gen() as $val)
{
    echo $val, PHP_EOL;
}
```

The above example will output:

```
1
2
3
4
```
