# preg_replace_callback_array()

The new preg_replace_callback_array() function enables code to be written more cleanly when using the preg_replace_callback() function. Prior to PHP 7, callbacks that needed to be executed per regular expression required the callback function to be polluted with lots of branching.

Now, callbacks can be registered to each regular expression using an associative array, where the key is a regular expression and the value is a callback.

```php
<?php
$subject = 'Aaaaaa Bbb';

preg_replace_callback_array(
    [
        '~[a]+~i' => function ($match) {
            echo strlen($match[0]), ' matches for "a" found', PHP_EOL;
        },
        '~[b]+~i' => function ($match) {
            echo strlen($match[0]), ' matches for "b" found', PHP_EOL;
        }
    ],
    $subject
);
```

The above example will output:

```
6 matches for "a" found
3 matches for "b" found
```
