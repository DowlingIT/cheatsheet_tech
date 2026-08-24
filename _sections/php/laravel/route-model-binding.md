---
title: Route Model Binding
subtopic: laravel
group: Routing
order: 2
---

#### Implicit binding

```php
// Resolves by primary key automatically
Route::get('/posts/{post}', function (Post $post) {
    return view('posts.show', compact('post'));
});

// Custom key (resolves by 'slug' column)
Route::get('/posts/{post:slug}', fn(Post $post) => $post);

// Override in model
public function getRouteKeyName(): string { return 'slug'; }
```

#### Explicit binding

```php
// bootstrap/app.php or RouteServiceProvider
Route::bind('post', function ($value) {
    return Post::where('slug', $value)->firstOrFail();
});
```

#### Scoped binding

```php
// /users/{user}/posts/{post} — post must belong to user
Route::get('/users/{user}/posts/{post}', fn(User $user, Post $post) => $post)
    ->scopeBindings();
```
