---
title: Concepts
subtopic: vim
group: General Use
order: 7
---

#### Modes & what they allow

| Mode | How to enter | What you can do |
|------|-------------|-----------------|
| Normal | `Esc` | move, delete, yank, run commands |
| Insert | `i a o` etc. | type new text |
| Visual | `v V Ctrl+V` | select then act |
| Command | `:` | search-replace, file ops |

Moving and searching (`/ ?`) work in **Normal** mode. Editing commands (`dd yy >`) also work in **Normal** mode — Insert mode is only for typing free text.

#### Yank

"Yank" is vim's word for copy. Yanked text goes into a register; `p` pastes it.

```
yy    yank (copy) current line
yw    yank word
y$    yank to end of line
```
