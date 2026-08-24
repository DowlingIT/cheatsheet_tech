---
title: Form Layout
subtopic: filament
group: Forms
order: 2
---

#### Layout components

```php
use Filament\Forms\Components\{Section, Grid, Tabs, Fieldset, Split};

Section::make('Content')
    ->description('Main post content')
    ->schema([
        TextInput::make('title'),
        RichEditor::make('body'),
    ])->columns(1)->collapsible(),

Grid::make(2)->schema([
    TextInput::make('first_name'),
    TextInput::make('last_name'),
]),

Tabs::make('Details')->tabs([
    Tabs\Tab::make('Content')->schema([...]),
    Tabs\Tab::make('SEO')->schema([
        TextInput::make('meta_title'),
        Textarea::make('meta_description'),
    ]),
]),

Fieldset::make('Address')->schema([
    TextInput::make('street'),
    TextInput::make('city'),
])->columns(2),
```
