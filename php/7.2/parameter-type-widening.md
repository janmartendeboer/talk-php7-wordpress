# Parameter type widening

This would provide an easier upgrade path for libraries to start using scalar types, to replace manual checks being done inside the methods, without requiring an update for all sub-classes.

Another example of this being useful is DateTime::createFromFormat(). This method is already documented to accept only a class of type DateTimeZone as the 3rd parameter in the manual, but the type declaration is not actually present in the implementation.

```php
<?php
class ArrayClass {
  public function foo(array $foo) { /* ... */ }
}

class EverythingClass extends ArrayClass {
  public function foo($foo) { /* ... */ }
}
```
