---
title: String Syntax
subtopic: php-core
group: Strings
order: 1
---

#### Quoting

```php
'No interpolation, literal \n and \\'
"Interpolates $var, {$arr['key']}, \n \t \\"
```

#### Heredoc & nowdoc

```php
$doc = <<<EOT
    Interpolates $name here.
    Trailing newline included.
    EOT;

$raw = <<<'EOT'
    No $interpolation — like single quote.
    EOT;
```

#### Useful string constants

```
PHP_EOL   PHP_INT_MAX   PHP_INT_MIN   PHP_EOL
DIRECTORY_SEPARATOR   PATH_SEPARATOR
```
