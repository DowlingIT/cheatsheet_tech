---
title: Magic Methods
subtopic: php-core
group: Classes & OOP
order: 3
---

#### Lifecycle & conversion

```
__construct(…)    called on new ClassName()
__destruct()      called on object destruction
__toString()      called on (string) cast / echo
__invoke(…)       called when object used as function ($obj())
__clone()         called on clone $obj
```

#### Property & method overloading

```
__get($name)           access undefined / inaccessible property
__set($name, $val)     assign undefined / inaccessible property
__isset($name)         isset() on undefined property
__unset($name)         unset() on undefined property
__call($name, $args)   call undefined method
__callStatic(…)        call undefined static method
```

#### Serialization & debug

```
__sleep()      called before serialize() — return prop names
__wakeup()     called after unserialize()
__serialize()  8.1 array-based serialization
__debugInfo()  controls var_dump() output
```
