---
title: Artisan Commands
subtopic: filament
group: Overview
order: 2
---

#### Install & panels

```bash
composer require filament/filament
php artisan filament:install --panels          # scaffold the default admin panel
php artisan make:filament-panel admin          # create an additional panel
php artisan filament:upgrade                   # rebuild assets after package update
php artisan vendor:publish --tag=filament-config
```

#### Resources

```bash
php artisan make:filament-resource Post           # basic resource
php artisan make:filament-resource Post --generate # auto-generate form + table from model
php artisan make:filament-resource Post --simple   # modal CRUD — no separate pages
php artisan make:filament-resource Post --soft-deletes  # include trashed filter/restore action
php artisan make:filament-resource Post --view     # add a view (read-only) page
```

#### Pages, widgets & relations

```bash
php artisan make:filament-page Settings           # app/Filament/Pages/Settings.php

php artisan make:filament-widget StatsOverview              # stats overview widget
php artisan make:filament-widget LatestPosts --table        # table widget
php artisan make:filament-widget RevenueChart               # chart widget

php artisan make:filament-relation-manager PostResource comments body
# generates app/Filament/Resources/PostResource/RelationManagers/CommentsRelationManager.php
```
