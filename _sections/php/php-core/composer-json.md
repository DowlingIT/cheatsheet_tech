---
title: composer.json
subtopic: php-core
group: Composer
order: 2
---

#### Structure

```json
{
  "name": "vendor/my-app",
  "require": {
    "php": "^8.2",
    "nesbot/carbon": "^3.0"
  },
  "require-dev": {
    "phpunit/phpunit": "^11.0"
  },
  "autoload": {
    "psr-4": { "App\\": "app/" }
  },
  "autoload-dev": {
    "psr-4": { "Tests\\": "tests/" }
  },
  "scripts": {
    "test": "phpunit",
    "lint": "phpcs src/"
  }
}
```

#### Version constraints

```
^2.0       >=2.0.0 <3.0.0   (compatible release — most common)
~2.1       >=2.1.0 <3.0.0
2.1.*      any 2.1.x patch
>=2.0 <3.0 explicit range
1.0.0      exact version (avoid)
*          any version (avoid)
```
