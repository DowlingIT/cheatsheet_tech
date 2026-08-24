---
title: Authentication
subtopic: laravel
group: Middleware & Auth
order: 2
---

#### Auth helpers

```php
Auth::check()              // bool — is authenticated?
Auth::user()               // User model or null
Auth::id()                 // user id or null
auth()->user()             // same via helper
$request->user()           // same via request

Auth::attempt(['email' => $e, 'password' => $p], $remember)
Auth::login($user)
Auth::loginUsingId($id)
Auth::logout()
Auth::guard('api')->user()  // named guard
```

#### Route protection

```php
Route::middleware('auth')->group(function () { ... });
Route::middleware(['auth', 'verified'])->group(function () { ... });

// Redirect unauthenticated users
// configure in bootstrap/app.php:
->withMiddleware(fn(Middleware $m) => $m->redirectGuestsTo('/login'))
```
