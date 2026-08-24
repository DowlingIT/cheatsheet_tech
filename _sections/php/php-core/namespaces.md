---
title: Namespaces
subtopic: php-core
group: Scope & Namespaces
order: 2
---

#### Declaring

```php
<?php
namespace App\Http\Controllers;   // must be first statement

class PostController { }
// Fully-qualified: \App\Http\Controllers\PostController
```

#### Importing with use

```php
use App\Models\Post;
use App\Models\User as AppUser;           // alias to avoid collision
use App\Services\{PostService, TagService}; // group import (7.0+)

use function App\Helpers\slugify;         // import a function
use const App\Constants\MAX_RETRIES;      // import a constant
```

#### Name resolution rules

```
Post                  // relative — looks in current namespace first
\Post                 // absolute — global Post class
App\Models\Post       // relative from current namespace root
\App\Models\Post      // absolute, fully-qualified (always unambiguous)
```
