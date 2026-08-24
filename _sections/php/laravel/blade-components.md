---
title: Blade Components & Layout
subtopic: laravel
group: Blade Templates
order: 2
render_with_liquid: false
---

#### Layout inheritance

```blade
{{-- resources/views/layouts/app.blade.php --}}
@yield('title', 'Default Title')
@yield('content')
@stack('scripts')

{{-- child view --}}
@extends('layouts.app')
@section('title', 'Posts')
@section('content')
    <h1>Posts</h1>
@endsection
@push('scripts') <script src="app.js"></script> @endpush
```

#### Anonymous components

```blade
{{-- resources/views/components/alert.blade.php --}}
<div class="alert alert-{{ $type ?? 'info' }}">
    {{ $slot }}
</div>

{{-- Usage --}}
<x-alert type="danger">Something went wrong.</x-alert>
<x-alert>Informational message.</x-alert>
```

#### Component directives

```blade
@auth … @endauth       @guest … @endguest
@can('update', $post) … @endcan
@include('partials.header', ['title' => 'Posts'])
@once … @endonce       (renders only first time in loop)
```
