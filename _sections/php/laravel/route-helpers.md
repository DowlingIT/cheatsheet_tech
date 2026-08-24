---
title: Route Helpers
subtopic: laravel
group: Routing
order: 3
---

#### URL generation

```php
route('posts.show', $post)           // → /posts/42
route('posts.show', ['id' => 42])    // explicit params
url('/posts/42')                     // absolute URL
secure_url('/checkout')              // https://
asset('images/logo.png')
```

#### Redirects

```php
return redirect()->route('posts.index');
return redirect('/posts')->with('success', 'Saved!');
return back();
return back()->withInput()->withErrors($validator);
```

#### Current route info

```php
request()->route()->getName()   // 'posts.show'
request()->routeIs('posts.*')   // true / false
Route::current()->uri()
Route::currentRouteName()
```
