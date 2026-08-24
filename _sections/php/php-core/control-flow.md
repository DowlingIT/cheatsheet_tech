---
title: Control Flow
subtopic: php-core
group: Language Reference
order: 1
---

#### Conditionals

```php
if ($x > 0) { } elseif ($x < 0) { } else { }

$label = match($status) {
    1, 2    => 'Active',
    default => 'Other',
};
```

#### Loops

```php
for ($i = 0; $i < 10; $i++) { }
foreach ($arr as $key => $val) { }
while ($cond) { }
do { } while ($cond);
```

#### Jump

```
break  continue  return  yield  goto
```
