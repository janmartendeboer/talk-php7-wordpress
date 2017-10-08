# Allow abstract function override

PHP 7 introduced type declarations for return and improved ones for parameters. They currently support a very limited kind of variance (only to no-type):

```php
<?php
class A           { function bar(stdClass $x){}  }
class B extends A { function bar($x): stdClass{} }
```

However, this isn't currently matched by the equivalent abstract declarations:

This RFC proposes to allow this, even if it has very few uses, and because there is no reason to disallow a compatible redefinition.

Additionally, it comes in handy for documentation:

```php
<?php
interface A{
    function doSomething();
}
 
interface B extends A{
    function doSomethingElse();
}
 
abstract class AProxy implements A{
    abstract protected function getOrigin(): A;
    function doSomething(){
        return $this->getOrigin()->doSomething();
    }
}
 
// This phpdoc syntax has quirks in phpdocumentor
// apigen and phpstorm, and it's almost unmanageable
// as phpdoc interpreters have poor multiline support
// (imagine documenting all the parameters, the return
// type, all the throws...):
/** @method B getOrigin() */
abstract class BProxy extends AProxy implements B{
    /** @return B */ // This is much better!
    abstract protected function getOrigin(): A;
    function doSomethingElse(){
        return $this->getOrigin()->doSomethingElse();
    }
}
```

And, obviously, it will gain more uses when PHP will support a full-featured type variance.


