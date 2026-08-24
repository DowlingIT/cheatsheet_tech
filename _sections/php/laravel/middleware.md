---
title: Middleware
subtopic: laravel
group: Middleware & Auth
order: 1
---

#### Creating middleware

```php
class CheckRole {
    public function handle(Request $request, Closure $next, string ...$roles): Response {
        if (!$request->user()?->hasAnyRole($roles)) {
            abort(403);
        }
        return $next($request);
    }
}
```

#### Register & apply (Laravel 11)

```php
// bootstrap/app.php
->withMiddleware(function (Middleware $m) {
    $m->alias(['role' => CheckRole::class]);
    $m->web(append: [EnsureSessionIsValid::class]);
    $m->api(prepend: [ForceJsonResponse::class]);
})

// On route
Route::get('/admin', fn() => ...)->middleware('role:admin,editor');
// On controller
$this->middleware('auth')->except(['index', 'show']);
```
