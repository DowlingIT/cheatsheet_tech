---
title: Relationships
subtopic: laravel
group: Eloquent ORM
order: 3
---

#### Relationship types

```php
$this->hasOne(Profile::class)
$this->belongsTo(User::class, 'user_id')
$this->hasMany(Comment::class)
$this->belongsToMany(Tag::class)->withPivot('order')->withTimestamps()
$this->hasOneThrough(Avatar::class, Profile::class)
$this->hasManyThrough(Post::class, User::class)

// Polymorphic
$this->morphMany(Image::class, 'imageable')
$this->morphTo()
```

#### Eager loading

```php
Post::with('user', 'tags')->get();
Post::with(['comments' => fn($q) => $q->latest()->limit(5)])->get();
Post::withCount('comments')->get();
Post::withSum('items', 'quantity')->get();

$post->load('tags');              // lazy eager load after retrieval
$posts->loadMissing('user');
```

#### Attach / sync (many-to-many)

```php
$post->tags()->attach([1, 2, 3]);
$post->tags()->detach(1);
$post->tags()->sync([2, 3]);      // removes unlisted
$post->tags()->syncWithoutDetaching([4]);
```
