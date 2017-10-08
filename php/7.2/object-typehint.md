# Object typehint

PHP 7 introduced scalar types for parameters and also for declaring return types for functions.

However it is not currently possible to declare that a function either needs to be passed an object as a parameter, or to declare that a function must return an object.

* Hydrators
* Data extractors
* Service containers and DIC libraries

## Parameter type

```php
<?php
function acceptsObject(object $obj) {
    ...
}
 
// This code can be statically analyzed to be correct
acceptsObject(json_decode('{}'));
 
// This code can be statically analyzed to be correct
acceptsObject(new \MyObject());
 
// This can be statically analysed to contain an error.
// and would throw an TypeError at runtime.
acceptsObject("Ceci n'est pas une object.");
```

## Return type

Functions and methods can be declared with an object return type, to enforce that the function must return an object.

```php
<?php
// This function can be statically analysed to conform to the
// return type
function correctFunction() : object {
    $obj = json_decode('{}');
 
    return $obj;
}
 
// This function can be statically analysed to contain an error
// and will also fail at runtime.
function errorFunction() : object {
    return [];
}
```

## Service container

For both service containers and dependency injection libraries, it is common to want to put services and other objects into the container.


```php
<?php
interface ServiceContainer {
  // Set service definition
  public function set(string $id, object $service);
 
  // Retrieve service object from container
  public function get(string $id) : object;
}
```
