---
title: Model Traits & Boot Hooks
subtopic: laravel
group: Traits
order: 2
---

#### Custom model trait

```php
// app/Models/Concerns/HasSlug.php
trait HasSlug {
    // boot{TraitName}() — static boot hook, once per model class
    protected static function bootHasSlug(): void {
        static::creating(fn($m) => $m->slug ??= Str::slug($m->title));
    }

    // initialize{TraitName}() — initializer, on every new instance
    protected function initializeHasSlug(): void {
        $this->mergeFillable(['slug']);
    }

    public function scopeWhereSlug($q, string $s) { return $q->where('slug', $s); }
}

class Post extends Model { use HasSlug; }
```

Convention: model traits ("concerns") live in `app/Models/Concerns/`.
