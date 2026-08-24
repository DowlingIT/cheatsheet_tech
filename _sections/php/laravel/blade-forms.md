---
title: Blade Forms
subtopic: laravel
group: Blade Templates
order: 3
render_with_liquid: false
---

#### CSRF & method spoofing

```blade
<form method="POST" action="{{ route('posts.store') }}">
    @csrf
    @method('PUT')   {{-- for PUT / PATCH / DELETE --}}
    ...
</form>
```

#### Old input & errors

```blade
<input name="title" value="{{ old('title', $post->title ?? '') }}">

@error('title')
    <span class="text-red-500">{{ $message }}</span>
@enderror

@if ($errors->any())
    <ul>
        @foreach ($errors->all() as $error)
            <li>{{ $error }}</li>
        @endforeach
    </ul>
@endif
```

#### Misc

```blade
{{ csrf_field() }}          {{-- hidden input --}}
{{ method_field('DELETE') }}

route('posts.show', $post)  url('/about')  asset('css/app.css')
```
