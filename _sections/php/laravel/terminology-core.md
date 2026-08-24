---
title: Core Concepts
subtopic: laravel
group: Terminology
order: 1
---

#### Architecture

```
MVC               Model-View-Controller — organises code into data, display, and logic
Service Container  IoC container that creates and injects class dependencies automatically
Service Provider   Bootstrap class that registers bindings and boots services (AppServiceProvider)
Facade            Static-style proxy to a container service — DB::, Auth::, Route::, Cache::
Middleware        Layer that wraps HTTP requests — runs before/after a controller (auth, CSRF)
Pipeline          Chain of callables that pass a value through — the basis of middleware
```

#### Request lifecycle

```
public/index.php → bootstrap → service providers → router → middleware
→ controller → response → middleware (outbound) → browser
```

#### Key files

```
bootstrap/app.php     application bootstrap — registers middleware, providers, exceptions
config/app.php        timezone, locale, providers, aliases
.env                  environment-specific values — never commit to source control
routes/web.php        web routes (session, CSRF)  api.php (stateless)
```
