# Iterable pseudo type

A new pseudo-type (similar to callable) called iterable has been introduced. It may be used in parameter and return types, where it accepts either arrays or objects that implement the Traversable interface. With respect to subtyping, parameter types of child classes may broaden a parent's declaration of array or Traversable to iterable. With return types, child classes may narrow a parent's return type of iterable to array or an object that implements Traversable.

```php
<?php
function iterator(iterable $iter)
{
    foreach ($iter as $val) {
        //
    }
}
```
