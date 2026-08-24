---
title: Plugins & Chaining
subtopic: jquery
group: Utilities & Plugins
order: 2
---

#### Writing a plugin

```js
$.fn.highlight = function (color = 'yellow') {
  return this.each(function () {          // `this` = the jQuery collection
    $(this).css('background', color);
  });
};

$('.card').highlight('pink').addClass('done');   // plugins chain like built-ins
```
