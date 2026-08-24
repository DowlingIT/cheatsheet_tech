---
title: Manage Stacks
subtopic: swarm
group: Stacks
order: 2
---

#### Inspecting & removing

```bash
docker stack ls                  # all stacks
docker stack services myapp        # services in a stack
docker stack ps myapp                # tasks in a stack
docker stack rm myapp                  # remove everything in the stack
```
