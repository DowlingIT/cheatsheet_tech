---
title: Trait Basics
subtopic: laravel
group: Traits
order: 1
---

#### Define & use

```php
// php artisan make:trait Traits/HasUuid   (Laravel 11+)
trait Loggable {
    protected array $log = [];               // properties allowed
    public function log(string $m): void { $this->log[] = $m; }
    abstract public function name(): string; // using class must implement
    public static function make(): static { return new static; }
}

class Order { use Loggable, HasUuid; }      // one class, several traits
```

#### Conflict resolution

```php
class Report {
    use Csv, Pdf {
        Pdf::export insteadof Csv;   // pick Pdf's export()
        Csv::export as exportCsv;    // keep Csv's under alias
        log as protected;            // change visibility
    }
}
```

Precedence: using class > trait > inherited parent method.
