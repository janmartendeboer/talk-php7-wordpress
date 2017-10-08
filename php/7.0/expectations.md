# Expectations

Expectations are a backwards compatible enhancement to the older assert() function. They allow for zero-cost assertions in production code, and provide the ability to throw custom exceptions when the assertion fails.

While the old API continues to be maintained for compatibility, assert() is now a language construct, allowing the first parameter to be an expression rather than just a string to be evaluated or a boolean value to be tested.

```php
<?php
ini_set('assert.exception', 1);

class CustomError extends AssertionError {}

assert(false, new CustomError('Some error message'));
```

The above example will output:

```
Fatal error: Uncaught CustomError: Some error message
```

Full details on this feature, including how to configure it in both development and production environments, can be found in the expectations section of the assert() reference.
