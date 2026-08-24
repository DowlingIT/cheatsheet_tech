---
title: Routes
subtopic: laravel
group: Routing
order: 1
---

#### Basic & resource routes

```php
Route::get('/posts', [PostController::class, 'index']);
Route::post('/posts', [PostController::class, 'store']);
Route::put('/posts/{post}', [PostController::class, 'update']);
Route::delete('/posts/{post}', [PostController::class, 'destroy']);

Route::resource('posts', PostController::class);
Route::apiResource('posts', PostController::class);
// only / except specific methods:
Route::resource('photos', PhotoController::class)->only(['index', 'show']);
```

#### Groups & constraints

```php
Route::middleware(['auth', 'verified'])->group(function () {
    Route::prefix('admin')->name('admin.')->group(function () {
        Route::resource('users', UserController::class);
    });
});

Route::get('/user/{id}', fn(int $id) => User::findOrFail($id))
    ->where('id', '[0-9]+')
    ->name('user.show');
```
