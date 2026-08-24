---
title: Notifications & Sorting
subtopic: filament
group: Tables
order: 3
---

#### Notifications

```php
use Filament\Notifications\Notification;

Notification::make()
    ->title('Post published')
    ->body('The post is now live.')
    ->success()
    ->send();

Notification::make()
    ->title('Error')
    ->body('Check required fields.')
    ->danger()
    ->persistent()
    ->send();

// Types: ->success()  ->warning()  ->danger()  ->info()
// Chainable: ->persistent()  ->duration(5000)  ->icon('…')
```

#### Table sorting & pagination

```php
// In table() method
->defaultSort('created_at', 'desc')
->defaultPaginationPageOption(25)
->paginationPageOptions([10, 25, 50, 100])
->striped()
->poll('30s')          // auto-refresh every 30 seconds
->deferLoading()       // lazy load on first render
->searchable()         // enables global search on searchable columns
```
