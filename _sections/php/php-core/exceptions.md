---
title: Exceptions
subtopic: php-core
group: Error Handling & Globals
order: 1
---

#### Try / catch / finally

```php
try {
    riskyOp();
} catch (DatabaseException $e) {
    log($e->getMessage());
} catch (RuntimeException | LogicException $e) {
    report($e);
} finally {
    cleanup();   // always runs
}

// Throw expression (8.0) — usable anywhere
$val = $input ?? throw new InvalidArgumentException('Required');
fn($x) => $x > 0 ? $x : throw new \RangeError;
```

#### Custom exceptions

```php
class NotFoundException extends RuntimeException {
    public function __construct(string $resource, int $id) {
        parent::__construct("$resource #$id not found", 404);
    }
}
```
