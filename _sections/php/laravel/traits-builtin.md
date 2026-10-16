---
title: Built-in Traits
subtopic: laravel
group: Traits
order: 3
---

#### Models

| Trait | Adds |
|---|---|
| `HasFactory` | `Post::factory()` |
| `SoftDeletes` | `deleted_at`, `withTrashed()`, `restore()` |
| `Notifiable` | `$user->notify(...)` |
| `HasApiTokens` | Sanctum `createToken()` |
| `HasUuids` / `HasUlids` | UUID/ULID primary keys |
| `Prunable` | `prunable()` + `model:prune` |

#### Jobs, events & tests

| Trait | Adds |
|---|---|
| `Dispatchable` | `Job::dispatch()` |
| `Queueable` | `onQueue()`, `delay()` |
| `InteractsWithQueue` | `release()`, `attempts()` |
| `SerializesModels` | queues model IDs, re-fetches on run |
| `RefreshDatabase` | resets DB per test |
