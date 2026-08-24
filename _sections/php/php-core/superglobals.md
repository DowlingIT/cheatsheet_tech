---
title: Superglobals
subtopic: php-core
group: Error Handling & Globals
order: 3
---

#### HTTP & session

```
$_GET        query string params
$_POST       POST body (form / urlencoded)
$_REQUEST    merged GET + POST + COOKIE
$_FILES      uploaded file metadata (name, tmp_name, size, error)
$_SESSION    server-side session data
$_COOKIE     cookies sent by the client
```

#### Session functions

```php
session_start();
$_SESSION['user'] = $user->id;
session_regenerate_id(true);    // after login
session_destroy();
```

#### Server & environment

```
$_SERVER['REQUEST_METHOD']   GET / POST / PUT …
$_SERVER['HTTP_HOST']        example.com
$_SERVER['DOCUMENT_ROOT']    /var/www/html
$_SERVER['REMOTE_ADDR']      client IP
$_ENV                        env vars (prefer getenv('KEY'))
$GLOBALS                     all globals — avoid in practice
```
