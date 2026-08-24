---
title: Conditionals
subtopic: python-core
group: Control Flow
order: 1
---

#### if / elif / else

```python
if x > 0:
    print('positive')
elif x == 0:
    print('zero')
else:
    print('negative')

result = 'yes' if condition else 'no'   # ternary expression
```

#### match / case (3.10+)

```python
match command:
    case 'quit':
        exit()
    case 'go' | 'move':
        move()
    case {'action': action, 'value': val}:
        handle(action, val)
    case Point(x=0, y=y):      # class pattern
        print(f'y={y}')
    case [first, *rest]:       # sequence pattern
        print(first, rest)
    case _:
        unknown()
```
