---
title: Basic Types
subtopic: go-core
group: Variables & Types
order: 2
---

#### Built-in types

```go
bool
string
int  int8  int16  int32  int64   uint  uint8 ...
float32  float64
byte   // alias for uint8
rune   // alias for int32 — a Unicode code point
```

#### Conversion

```go
i := 42
f := float64(i)
s := strconv.Itoa(i)
n, err := strconv.Atoi("42")
```
