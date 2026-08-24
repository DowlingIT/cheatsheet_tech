---
title: Model Setup
subtopic: laravel
group: Eloquent ORM
order: 2
---

#### Model class

```php
class Post extends Model {
    use SoftDeletes;

    protected $fillable = ['title', 'body', 'status', 'user_id'];
    protected $hidden   = ['secret_token'];
    protected $appends  = ['full_url'];     // adds accessor to JSON

    protected $casts = [
        'published_at' => 'datetime',
        'settings'     => 'array',
        'status'       => Status::class,    // enum cast (8.1)
    ];

    // Accessor / mutator (8.0+ style)
    protected function title(): Attribute {
        return Attribute::make(
            get: fn($v) => Str::title($v),
            set: fn($v) => strtolower($v),
        );
    }

    protected function fullUrl(): Attribute {
        return Attribute::make(
            get: fn() => url('/posts/' . $this->slug)
        );
    }
}
```
