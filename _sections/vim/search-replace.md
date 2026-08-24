---
title: Search & Replace
subtopic: vim
group: General Use
order: 5
---

#### Search

```
/pattern        search forward
?pattern        search backward
n               next match
N               previous match
*               search word under cursor
#               search word under cursor (backward)
```

#### Replace

```
:%s/old/new/g       replace all in file
:%s/old/new/gc      replace all with confirm
:s/old/new/g        replace in current line
:5,10s/old/new/g    replace in lines 5–10
```
