---
title: Functions
subtopic: go-core
group: Functions
order: 1
---

#### Multiple & named returns

```go
func divide(a, b int) (int, error) {
    if b == 0 {
        return 0, errors.New("division by zero")
    }
    return a / b, nil
}

func split(sum int) (x, y int) {   // named returns
    x = sum * 4 / 9
    y = sum - x
    return   // "naked" return — uses the named values
}
```

#### Variadic

```go
func sum(nums ...int) int {
    total := 0
    for _, n := range nums { total += n }
    return total
}
sum(1, 2, 3)
sum(slice...)   // spread a slice into variadic args
```
