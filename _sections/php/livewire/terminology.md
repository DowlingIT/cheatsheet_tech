---
title: Concepts & Terms
subtopic: livewire
group: Overview
order: 1
---

#### How Livewire works

```
Hydration      Server converts PHP component state → JSON snapshot + HTML for the browser
Dehydration    Browser posts user interaction → server rebuilds PHP component from snapshot
Morphing       DOM-diffing algorithm that patches only changed elements (no full reload)
Snapshot       JSON payload round-tripped between browser and server on every request
Nesting        A Livewire component rendered inside another — each has its own lifecycle
```

#### Feature terms

```
wire:model     Two-way data binding between an input and a PHP public property
wire:navigate  SPA-mode navigation — swaps page content without full browser reload
Polling        wire:poll — component auto-refreshes on a timer (e.g. every 5s)
Lazy loading   #[Lazy] — defer component render until after the page has loaded
Entangle       @entangle — sync a Livewire property with an Alpine.js x-data value
Wireable       Interface allowing a custom class to be stored in a Livewire property
```

#### Relationship to the stack

```
Laravel   backend framework — Livewire runs inside it as a package
Alpine.js lightweight JS sprinkles — pairs with Livewire for client-only behaviour
Blade     templating engine — Livewire components render standard Blade views
Folio     page-based routing — can colocate a Livewire component with its route
Volt      single-file component syntax (class + template in one .blade.php file)
```
