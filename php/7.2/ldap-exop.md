# LDAP EXOP

```php
<?php
// Call EXOP whoami and store the result in $identity
if (ldap_exop($link, LDAP_EXOP_WHO_AM_I, NULL, $identity)) {
  echo "Connected as $identity\n";
} else {
  echo "Operation failed\n";
}
// Same thing using a result object
$r = ldap_exop($link, LDAP_EXOP_WHO_AM_I);
if (($r !== FALSE) && ldap_parse_exop($link, $r, $retdata)) {
  echo "Connected as $retdata\n";
} else {
  echo "Operation failed\n";
}
// Same thing with the helper
if (ldap_exop_whoami($link, $identity)) {
  echo "Connected as $identity\n";
} else {
  echo "Operation failed\n";
}
// Changing password with the helper
if (ldap_exop_passwd($link, 'uid=johndoe,dc=example,dc=com', '', 'newpassword')) {
  echo "Password changed\n";
} else {
  echo "Operation failed\n";
}
```
