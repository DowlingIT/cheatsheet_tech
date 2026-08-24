---
title: Async & Event Terms
subtopic: laravel
group: Terminology
order: 3
---

#### Queues & jobs

```
Queue     Named list of background work — default, emails, high, low (configurable)
Job       Dispatchable class that runs asynchronously on a queue worker
Worker    Process that picks up jobs from the queue — php artisan queue:work
Horizon   Laravel dashboard for Redis queues — monitoring, metrics, retries
Scheduler Cron-like task runner defined in code — php artisan schedule:run (every minute)
```

#### Events, listeners & observers

```
Event      Plain PHP class representing something that happened — OrderPlaced, UserRegistered
Listener   Handles an event — can be queued, can handle multiple events
Observer   Groups a model's lifecycle hooks in one class (creating, created, updated, deleted)
```

#### Notifications & broadcasting

```
Notification  Sendable object supporting multiple channels from one class
Channel       Notification delivery method — mail, database, broadcast, Slack, SMS
Broadcast     Push events to browser over WebSocket — via Pusher, Reverb (native), or Ably
Echo          Laravel's JavaScript library for listening to broadcast events
```

#### Blade & frontend

```
Blade      PHP templating engine — compiles @directives to cached PHP files
Component  Reusable Blade class+view pair — x-alert, x-modal
Slot       Named placeholder inside a component (like a prop for HTML content)
Vite       Frontend build tool replacing Mix — bundles CSS/JS, HMR in development
```
