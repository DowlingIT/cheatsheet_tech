---
title: Regex
subtopic: vim
group: General Use
order: 8
---

Vim's `/`, `?`, and `:s/` use a full regex engine — not glob wildcards. It supports lookaheads, backreferences, non-greedy matching, and more. The dialect differs from PCRE: most metacharacters need a backslash by default.

#### Default vs `\v` (very magic)

```
/colou\?r          default: \? = zero or one
/\vcolou?r         \v mode: ? = zero or one (PCRE-like)
```

Prefixing with `\v` makes most punctuation special without backslashes — closer to the regex you'd write anywhere else.

#### Examples (not exhaustive)

```
\w\+               one or more word characters
\d\{3}             exactly 3 digits
foo\|bar           "foo" or "bar"
^\s*               leading whitespace
\<word\>           whole word (not a substring)
\(foo\)\@!         negative lookahead for "foo"
```

#### Backreferences in substitution

```
:%s/\(\w\+\)/[\1]/g       wrap each word in brackets
:%s/\v(\w+)/[\1]/g        same, using \v
```

Full reference: `:help pattern` inside vim.
