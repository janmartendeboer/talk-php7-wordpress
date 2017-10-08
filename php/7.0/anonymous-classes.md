# Anonymous classes

Support for anonymous classes has been added via new class. These can be used in place of full class definitions for throwaway objects:

```php
<?php
interface Logger {
    public function log(string $msg);
}

class Application {
    private $logger;

    public function getLogger(): Logger {
         return $this->logger;
    }

    public function setLogger(Logger $logger) {
         $this->logger = $logger;
    }
}

$app = new Application;
$app->setLogger(new class implements Logger {
    public function log(string $msg) {
        echo $msg;
    }
});

var_dump($app->getLogger());
```

The above example will output:

```
object(class@anonymous)#2 (0) {
}
```

Full documentation can be found in the anonymous class reference.
