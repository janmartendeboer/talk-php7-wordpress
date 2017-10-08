# Closure::call

Closure::call() is a more performant, shorthand way of temporarily binding an object scope to a closure and invoking it.

```php
<?php
class A {private $x = 1;}

// Pre PHP 7 code
$getX = function() {return $this->x;};
$getXCB = $getX->bindTo(new A, 'A'); // intermediate closure
echo $getXCB();

// PHP 7+ code
$getX = function() {return $this->x;};
echo $getX->call(new A);
```

The above example will output:

```
1
1
```
