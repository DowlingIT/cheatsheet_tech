---
title: Trait Terms
subtopic: laravel
group: Terminology
order: 4
---

#### Traits & concerns

```
Trait             Reusable methods/properties copied into a class at compile time — can't be instantiated
Using class       The class that includes a trait — class Post { use HasSlug; }
use (class body)  Includes a trait — not the same as a top-of-file namespace import
Horizontal reuse  Sharing code across unrelated classes without inheritance
Concern           Laravel's name for a single-behaviour trait — Models/Concerns/, HasAttributes
Composition       A trait that itself uses other traits
```

#### Conflicts & hooks

```
insteadof            Pick one trait's method when two traits define the same name
as                   Alias a trait method, or change its visibility
boot{Trait}          Static hook Eloquent runs once per model class — register model events
initialize{Trait}    Hook Eloquent runs on every new model instance — merge fillable, casts
class_uses_recursive Helper: all traits on a class, its parents, and nested traits
```
