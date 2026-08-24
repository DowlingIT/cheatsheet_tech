---
title: Include & Require
subtopic: php-core
group: Scope & Namespaces
order: 3
---

#### Behaviour differences

```
require       E_ERROR (fatal) if file not found — stops execution
include       E_WARNING if file not found — execution continues
require_once  same as require, but skips if already loaded
include_once  same as include, but skips if already loaded
```

#### Usage

```php
require __DIR__ . '/config.php';
require_once __DIR__ . '/../vendor/autoload.php';
include 'optional-widget.php';

// Included file can return a value
$config = require __DIR__ . '/config.php';
// config.php ends with: return ['debug' => true];
```

#### When to use which

```
require_once   class files, autoloaders, critical config
include        optional template fragments, views
```

Prefer Composer autoloading (`vendor/autoload.php`) over
manual `require_once` for all class-based code.
