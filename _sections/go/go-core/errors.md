---
title: Errors
subtopic: go-core
group: Error Handling
order: 1
---

#### error interface & wrapping

```go
type NotFoundError struct { ID int }
func (e *NotFoundError) Error() string { return fmt.Sprintf("id %d not found", e.ID) }

err := fmt.Errorf("loading user: %w", &NotFoundError{ID: 1})   // %w wraps

var nfe *NotFoundError
errors.As(err, &nfe)            // unwraps the chain looking for a matching type
errors.Is(err, sql.ErrNoRows)     // unwraps looking for a matching sentinel value
```
