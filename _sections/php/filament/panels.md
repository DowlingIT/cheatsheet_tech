---
title: Panel Config
subtopic: filament
group: Resources & Navigation
order: 2
---

#### Panel provider

```php
// app/Providers/Filament/AdminPanelProvider.php
public function panel(Panel $panel): Panel {
    return $panel
        ->default()
        ->id('admin')
        ->path('admin')
        ->login()
        ->colors(['primary' => Color::Amber])
        ->discoverResources(
            in: app_path('Filament/Resources'),
            for: 'App\\Filament\\Resources'
        )
        ->discoverPages(
            in: app_path('Filament/Pages'),
            for: 'App\\Filament\\Pages'
        )
        ->navigationGroups(['Content', 'Settings'])
        ->authMiddleware([Authenticate::class]);
}
```

#### Navigation badges

```php
// In any Resource
public static function getNavigationBadge(): ?string {
    return static::getModel()::where('status', 'draft')->count() ?: null;
}
public static function getNavigationBadgeColor(): ?string { return 'warning'; }
```
