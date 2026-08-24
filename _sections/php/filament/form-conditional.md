---
title: Conditional Fields
subtopic: filament
group: Forms
order: 3
---

#### Reactive fields

```php
use Filament\Forms\Get;
use Filament\Forms\Set;

Toggle::make('is_company')->live(),   // re-renders on change

TextInput::make('company_name')
    ->visible(fn(Get $get): bool => $get('is_company') === true),

TextInput::make('discount')
    ->hidden(fn(Get $get): bool => $get('status') !== 'active'),

TextInput::make('email')
    ->disabled(fn(Get $get): bool => $get('sso_enabled')),
```

#### Cascading selects

```php
Select::make('country_id')
    ->options(Country::pluck('name', 'id'))
    ->live()
    ->afterStateUpdated(fn(Set $set) => $set('state_id', null)),

Select::make('state_id')
    ->options(fn(Get $get) => State::where('country_id', $get('country_id'))
                                    ->pluck('name', 'id')),
```

#### Common field modifiers

```php
->required()    ->nullable()    ->disabled()
->readOnly()    ->dehydrated(false)    ->hidden()
->helperText('…')    ->hint('…')    ->hintIcon('…')
->placeholder('…')  ->prefix('$')  ->suffix('.00')
```
