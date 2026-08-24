---
title: Error Functions
subtopic: php-core
group: Error Handling & Globals
order: 2
---

#### Error levels

```
E_ERROR      E_WARNING     E_NOTICE
E_DEPRECATED E_USER_ERROR  E_ALL
```

#### Handlers & logging

```php
set_error_handler(function(int $errno, string $msg, string $file, int $line): bool {
    error_log("[$errno] $msg in $file:$line");
    return true;   // suppress default PHP handler
});

set_exception_handler(function(\Throwable $e): void {
    error_log($e->getMessage());
});

restore_error_handler();
restore_exception_handler();

error_log('message');           // to PHP error log
trigger_error('msg', E_USER_WARNING);
```

#### Debug helpers

```php
var_dump($val)      print_r($val)     var_export($val)
debug_backtrace()   debug_print_backtrace()
```
