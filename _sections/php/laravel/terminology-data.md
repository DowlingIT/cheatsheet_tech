---
title: Data & ORM Terms
subtopic: laravel
group: Terminology
order: 2
---

#### Eloquent & database

```
Eloquent        Laravel's Active Record ORM — each Model class maps to one DB table
Model           Eloquent class representing a DB table (app/Models/Post.php → posts table)
Query Builder   Fluent SQL builder without models — DB::table('posts')->where(…)->get()
Migration       Versioned schema change file — tracks and rolls back DB structure changes
Seeder          Class that populates DB with data — used in development and testing
Factory         Fake-data blueprint for a model — Post::factory()->count(10)->create()
Scope           Reusable query constraint — local ($query->active()) or global (auto-applied)
Accessor        Computed / formatted property on a model — read-only transformation
Mutator         Transform a value before it is stored in the database
Cast            Auto-convert a DB column to a PHP type — array, datetime, enum, bool
Tinker          Interactive REPL for running Eloquent queries and PHP code (php artisan tinker)
```

#### Collections

```
Collection       Fluent wrapper around arrays — map, filter, reduce, pluck, groupBy, …
Lazy Collection  Generator-based collection — loads items on demand (low memory usage)
```
