# domain-whois

This package contains a class that can fetch DNS records and whois info.

``composer require nzldev/domain-whois``

## Example of usage

```php
<?php

$sld = 'google.com';

$domain = new NzlDev\Whois\Whois($sld);

$whois_answer = $domain->info();

echo $whois_answer;

if ($domain->isAvailable()) {
    echo "Domain is available\n";
} else {
    echo "Domain is registered\n";
}
```

A more complete example:

```php
<?php
require_once __DIR__.'/vendor/autoload.php';

$sld = 'facebook.com';

try {
  $domain = new NzlDev\Whois\Whois($sld);
} catch (InvalidArgumentException $e) {
  die($e->getMessage()."\n");
}

if ($domain->isAvailable()) {
  echo "Domain is available\n";
} else {
  echo "Domain is registered\n";
}
```
