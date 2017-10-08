# Convert callables to Closures with Closure::fromCallable()

A new static method has been introduced to the Closure class to allow for callables to be easily converted into Closure objects.

```php
<?php
class Test
{
    public function exposeFunction()
    {
        return Closure::fromCallable([$this, 'privateFunction']);
    }

    private function privateFunction($param)
    {
        var_dump($param);
    }
}

$privFunc = (new Test)->exposeFunction();
$privFunc('some value');
```

The above example will output:

```
string(10) "some value"
```
