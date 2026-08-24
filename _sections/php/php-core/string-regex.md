---
title: Regex
subtopic: php-core
group: Strings
order: 3
---

#### Functions

```php
preg_match('/^\d+$/', $s, $matches)      // first match
preg_match_all('/\d+/', $s, $all)        // all matches
preg_replace('/\s+/', ' ', $s)           // replace
preg_split('/[\s,]+/', $s)               // split
preg_quote($s, '/')                      // escape for use in pattern
```

#### Common patterns

```
/^\d+$/          only digits
/^[\w.+-]+@/     email start
/\bword\b/       whole word
```

#### Flags (inline)

```
(?i)   case-insensitive
(?m)   multiline (^ and $ match line boundaries)
(?s)   dotall (. matches newline)
(?:…)  non-capturing group
```
