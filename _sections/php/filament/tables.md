---
title: Table Columns
subtopic: filament
group: Tables
order: 1
---

#### Common columns

```php
use Filament\Tables\Columns\{TextColumn, ImageColumn, IconColumn, BadgeColumn, ToggleColumn};

TextColumn::make('title')->searchable()->sortable()->limit(50)->copyable(),
TextColumn::make('user.name')->label('Author')->sortable(),

TextColumn::make('status')
    ->badge()
    ->color(fn(string $state) => match($state) {
        'published' => 'success',
        'draft'     => 'warning',
        default     => 'gray',
    }),

ImageColumn::make('avatar')->circular(),
IconColumn::make('featured')->boolean(),
ToggleColumn::make('active'),

TextColumn::make('created_at')
    ->dateTime()
    ->sortable()
    ->toggleable(isToggledHiddenByDefault: true),
```
