---
title: Widgets
subtopic: filament
group: Resources & Navigation
order: 4
---

#### Stats widget

```php
use Filament\Widgets\StatsOverviewWidget as BaseWidget;
use Filament\Widgets\StatsOverviewWidget\Stat;

class StatsOverview extends BaseWidget {
    protected function getStats(): array {
        return [
            Stat::make('Total Users', User::count())
                ->description('All time')->icon('heroicon-o-users')->color('primary'),
            Stat::make('Posts', Post::count())
                ->description('Published: ' . Post::published()->count())->color('success'),
            Stat::make('Revenue', '$' . number_format($total, 2))
                ->chart([7, 2, 10, 3, 15, 4, 17]),   // sparkline
        ];
    }
}
```

#### Table widget

```php
class LatestPosts extends TableWidget {
    protected function getTableQuery(): Builder {
        return Post::latest()->limit(5);
    }
    protected function getTableColumns(): array {
        return [
            TextColumn::make('title'),
            TextColumn::make('user.name')->label('Author'),
            TextColumn::make('created_at')->dateTime()->sortable(),
        ];
    }
}
```

#### Register widgets

```php
// On a panel (dashboard)
->widgets([StatsOverview::class, LatestPosts::class])

// On a resource page
protected function getHeaderWidgets(): array { return [PostStats::class]; }
protected function getFooterWidgets(): array { return [LatestPosts::class]; }
```
