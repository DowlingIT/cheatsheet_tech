---
title: Selectors
subtopic: jquery
group: Selectors & Traversal
order: 1
---

#### CSS-style selectors

```js
$('.card')                     // class
$('#app')                        // id
$('div.card[data-id]')             // attribute selector
$('li:first')   $('li:last')         // jQuery pseudo-selectors
$('li:eq(2)')                            // index-based
```

#### Filtering

```js
$('.card').filter('.active')
$('.card').not('.disabled')
$('.card').eq(0)
$('.card').first()   $('.card').last()
```
