# Unicode codepoint escape syntax

This takes a Unicode codepoint in hexadecimal form, and outputs that codepoint in UTF-8 to a double-quoted string or a heredoc. Any valid codepoint is accepted, with leading 0's being optional.

```php
<?php
echo "\u{aa}";
echo "\u{0000aa}";
echo "\u{9999}";
```

The above example will output:

```
ª
ª (same as before but with optional leading 0's)
香
```
