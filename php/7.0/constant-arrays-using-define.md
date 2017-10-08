# Constant arrays using define

Array constants can now be defined with define(). In PHP 5.6, they could only be defined with const.

```php
<?php
define('ANIMALS', [
    'dog',
    'cat',
    'bird'
]);

echo ANIMALS[1]; // outputs "cat"
```
