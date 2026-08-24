---
title: Blade Basics
subtopic: laravel
group: Blade Templates
order: 1
render_with_liquid: false
---

#### Output & conditionals

```blade
{{ $var }}              {{-- escaped output --}}
{!! $html !!}           {{-- unescaped (XSS risk) --}}
{{ $var ?? 'default' }}
{{-- comment (not rendered) --}}

@if ($user->isAdmin()) Admin
@elseif ($user->isMod()) Mod
@else Guest
@endif

@unless ($user->banned) Content @endunless
@isset($var) … @endisset
@empty($items) No items. @endempty
```

#### Loops

```blade
@foreach ($posts as $post)
    {{ $loop->index }}  {{ $loop->iteration }}
    {{ $loop->first ? 'first' : '' }}
    {{ $loop->last ? 'last' : '' }}
    {{ $post->title }}
@endforeach

@forelse ($posts as $post)
    {{ $post->title }}
@empty
    No posts found.
@endforelse

@for ($i = 0; $i < 10; $i++) {{ $i }} @endfor
@while ($cond) … @endwhile
```
