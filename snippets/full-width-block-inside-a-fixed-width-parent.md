---
title: Full-Width Block Inside a Fixed-Width Parent
date: 2019-04-13
languages: [CSS]
scripts: [relative_date.js, code_selector.js]
styles: [prism.css]
description: This snippet makes it possible to create full-width blocks inside a parent that has fixed width
---

This snippet makes it possible to create full-width blocks inside a parent that has fixed width (e.g. content wrapper and full-width image inside it).

## CSS

```CSS
.full {
  width: 100vw;
  margin-left: 50%;
  transform: translateX(-50%)
}
```

By [Andy Bell](//andy-bell.design/wrote/creating-a-full-bleed-css-utility/).