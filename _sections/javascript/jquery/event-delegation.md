---
title: Delegation & Ready
subtopic: jquery
group: Events
order: 2
---

#### Delegated events & document ready

```js
$('#list').on('click', '.item', function () {
  $(this).toggleClass('selected');   // `this` = the matched .item, not #list
});

$(document).ready(function () { });   // DOM ready
$(function () { });                     // shorthand for the above
```
