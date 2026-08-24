---
title: Magic Constants
subtopic: php-core
group: Language Reference
order: 4
---

#### Resolved at compile time

```
__LINE__       current line number in the file
__FILE__       full absolute path to the current file
__DIR__        directory of the current file (no trailing slash)
__FUNCTION__   current function name (or '' if outside)
__CLASS__      current class name (including namespace)
__TRAIT__      current trait name
__METHOD__     ClassName::methodName — includes class prefix
__NAMESPACE__  current namespace ('' in global namespace)
```

#### Class introspection

```php
ClassName::class         // 'Fully\Qualified\ClassName' — no autoload needed
get_class($obj)          // class name of an instance
get_parent_class($obj)   // parent class name
is_a($obj, 'App\Model')  // true if instance or child
```
