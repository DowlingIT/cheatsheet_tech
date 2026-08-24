---
title: Blade Includes
subtopic: laravel
group: Blade Templates
order: 4
render_with_liquid: false
---

#### @include variants

```blade
@include('partials.header')
@include('partials.nav', ['active' => 'home'])   {{-- pass extra data --}}

@includeIf('partials.sidebar')                   {{-- silently skip if view not found --}}
@includeWhen($user->isAdmin(), 'admin.menu')     {{-- include only when condition is true --}}
@includeUnless($user->banned, 'partials.feed')
@includeFirst(['custom.header', 'default.header']) {{-- first view that exists --}}
```

#### @each (loop include)

```blade
{{-- render 'partials.post-card' for each $posts item, variable name 'post' --}}
{{-- renders 'partials.empty' when $posts is empty --}}
@each('partials.post-card', $posts, 'post', 'partials.empty')
```

#### @extends, @yield, @section

```blade
{{-- layouts/app.blade.php --}}
<title>@yield('title', 'My App')</title>
@yield('content')
@stack('scripts')

{{-- child view --}}
@extends('layouts.app')
@section('title', 'Posts')
@section('content')
    @parent         {{-- keep parent content and append below --}}
    <h1>Posts</h1>
@endsection
@push('scripts') <script src="app.js"></script> @endpush
@prepend('scripts') <script src="head.js"></script> @endprepend
```
