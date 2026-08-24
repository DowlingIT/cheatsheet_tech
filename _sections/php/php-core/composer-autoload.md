---
title: Autoloading
subtopic: php-core
group: Composer
order: 3
---

#### PSR-4 (standard)

```json
"autoload": {
  "psr-4": {
    "App\\": "app/",
    "Database\\": "database/"
  }
}
```

Namespace `App\Models\Post` → file `app/Models/Post.php`

#### Bootstrap in entry point

```php
require __DIR__ . '/vendor/autoload.php';
```

#### Regenerate after changes

```bash
composer dump-autoload
composer dump-autoload --optimize    # classmap — faster, use in production
```

#### Other strategies

```json
"autoload": {
  "classmap": ["src/", "lib/"],       // scans dirs, maps class→file
  "files": ["src/helpers.php"]        // always-loaded files (for functions)
}
```
