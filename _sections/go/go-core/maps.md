---
title: Maps
subtopic: go-core
group: Collections
order: 2
---

#### Map operations

```go
m := map[string]int{"a": 1, "b": 2}
m["c"] = 3
v, ok := m["a"]        // ok is false if the key doesn't exist
delete(m, "a")
for k, v := range m { }   // iteration order is randomized
len(m)
```
