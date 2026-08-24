---
title: Eloquent Queries
subtopic: laravel
group: Eloquent ORM
order: 1
---

#### Retrieve

```php
Post::all();
Post::find(1);
Post::findOrFail(1);
Post::first();          Post::firstOrFail();
Post::firstOrCreate(['slug' => $slug], ['title' => $title]);
Post::firstOrNew(['slug' => $slug]);

Post::where('status', 'published')
    ->whereNotNull('published_at')
    ->whereIn('user_id', [1, 2, 3])
    ->whereBetween('views', [100, 1000])
    ->orderByDesc('created_at')
    ->limit(10)
    ->get();
```

#### Aggregate & mutate

```php
Post::where('active', true)->count();
Post::sum('views');   Post::avg('rating');   Post::max('views');

Post::create(['title' => 'Hello']);   // needs $fillable
$post->update(['title' => 'New']);
$post->delete();
Post::destroy([1, 2, 3]);
Post::upsert($rows, uniqueBy: ['slug'], update: ['title', 'body']);
Post::truncate();
```
