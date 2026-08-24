---
title: Composer CLI
subtopic: php-core
group: Composer
order: 1
---

#### Packages

```bash
composer init                           # create composer.json interactively
composer require vendor/package         # add & install
composer require vendor/package:^2.0   # with version constraint
composer require --dev phpunit/phpunit  # dev-only dependency

composer install                        # install from composer.lock (CI/prod)
composer update                         # update to latest allowed versions
composer update vendor/package          # update one package
composer remove vendor/package
```

#### Info & diagnostics

```bash
composer show                   # list installed packages
composer outdated               # packages with newer versions available
composer why vendor/package     # why is this installed?
composer validate               # check composer.json is valid
composer diagnose               # check environment
```

#### Popular packages

```
nesbot/carbon       datetime library
guzzlehttp/guzzle   HTTP client
vlucas/phpdotenv    .env file loading
phpunit/phpunit     testing framework
monolog/monolog     PSR-3 logging
```
