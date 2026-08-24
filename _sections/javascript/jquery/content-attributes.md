---
title: Content & Attributes
subtopic: jquery
group: DOM Manipulation
order: 1
---

#### Reading & writing content

```js
$el.text()          $el.text('New text')
$el.html()            $el.html('<b>Bold</b>')
$el.val()               $el.val('new value')       // form inputs
$el.attr('href')          $el.attr('href', url)
$el.data('id')               $el.data('id', 42)       // reads/writes data-id
```

#### Insert & remove

```js
$el.append('<li>New</li>')   $el.prepend(item)
$el.before(item)   $el.after(item)
$el.remove()   $el.empty()      // empty() clears children, keeps el itself
$el.clone()
```
