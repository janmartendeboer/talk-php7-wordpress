# Allow loading extensions by name

Today, 'extension=' and 'zend_extension=' lines in php.ini must contain the extension's file name. Unfortunately, the filename depends on the platform PHP is running on:

1. On Unix-like environments, the file name has the form '<extension-name>
.<suffix>'. <suffix> is 'so' on every system, except HP-UX, where it is 'sl'.
2. On Windows, the file name has the form 'php_<extension-name>.dll'.
While seasoned PHP administrators are used to this mechanism, this is a real issue for newcomers.

Under Unix/Linux, the typical mistake is to uncomment an 'extension=php_xxx.dll' line in the php.ini file.

On Windows, the situation for newcomers is still more confusing, as the distributed 'php.ini' files wrongly state that the Windows syntax is 'extension=modulename.extension', giving the wrong example of 'extension=mysqli.dll'. Ten lines below, the '.ini' file contains the right ';extension=php_mysql.dll' syntax but these conflicting directives are very confusing.

The issue may also appear when writing documentation and platform-agnostic scripts.

In addition to file names, it adds support for bare extension name. Note that the current syntax, using file names, remains supported as before.

Example:

```
extension=bz2
zend_extension=xdebug
```

'extension=bz2', for example, will cause PHP to load a file named 'php_bz2.dll' on Windows, a file named 'bz2.so' on Linux, and a file named 'bz2.sl' on HP-UX.

Example php.ini files are modified because loading extensions by name becomes the recommended way of configuring additional extensions to load. File names remain supported as legacy.

