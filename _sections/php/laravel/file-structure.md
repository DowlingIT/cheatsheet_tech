---
title: File Structure
subtopic: laravel
group: Artisan CLI
order: 1
---

#### Project layout

```
app/
  Http/
    Controllers/       request handlers
    Middleware/        request pipeline layers
    Requests/          form validation classes
  Models/              Eloquent model classes
  Policies/            authorization rules
  Jobs/                queued job classes
  Events/  Listeners/  event system
  Observers/           model lifecycle hooks
  Notifications/       mail / SMS / Slack messages
  Providers/           service providers (app bootstrap)
  Console/Commands/    custom artisan commands

config/                config files (app, database, mail, queue, …)
database/
  migrations/          schema version history
  seeders/             data population scripts
  factories/           fake data blueprints

resources/
  views/               Blade templates (.blade.php)
  css/ js/             source assets (compiled by Vite)

routes/
  web.php              browser routes (session, CSRF, cookies)
  api.php              API routes (stateless, token auth)
  console.php          closure-based artisan commands

storage/               logs, file uploads, cache, compiled views
public/                web root — index.php + compiled assets
tests/
  Feature/             integration tests (HTTP, DB)
  Unit/                isolated unit tests

.env                   environment variables (never commit)
composer.json          PHP dependencies
vite.config.js         frontend build config
```
