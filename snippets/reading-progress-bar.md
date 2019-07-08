---
title: Reading Progress Bar
date: 2019-04-13
languages: [HTML, CSS, JavaScript]
scripts: [relative_date.js]
styles: [prism.css]
description: This snippet will help you create a progress bar indicating reading progress.
---

This snippet will help you create a progress bar indicating reading progress. You can see them while reading posts on different websites.

## HTML

```html
<progress id="reading"></progress>
```

## CSS

```css
#reading {
    height: .25rem;
    position: fixed;
    top: 0;
    border: 0;
    background: blue;
    width: 0%;
}
```

## JavaScript

```javascript
var main, bar;

// declare vars once so that they are not redefined every scroll event
document.addEventListener("DOMContentLoaded", () => {
    main = document.querySelector("main"); // locate here your content element to count progress in
    bar = document.getElementById("reading");
});

window.addEventListener("scroll", () => {
    let top = main.getBoundingClientRect().top + window.scrollY; // find where content element starts
    let bottom = top + main.offsetHeight; // find where content element ends

    // if the user has started scrolling inside the target element
    if (window.scrollY >= top) {
        let progress = (window.scrollY - top) / main.clientHeight; // count part of element we've scrolled

        // or, if the target element remains visible when document ends
        if (document.body.offsetHeight - bottom <= window.innerHeight)
            progress = (window.scrollY - top) / (document.body.offsetHeight - window.innerHeight);

        if (progress <= 1)
            bar.style.width = parseFloat(progress * 100).toFixed(2) + "%";
        else bar.style.width = "100%"; // to avoid progress bar being stuck a bit less than 100%
    } else bar.style.width = "0%"; // to avoid progress bar being stuck a bit more than 0%
});
```

### What does it actually do?

Here’s the algorithm implemented in the code above:

1.  Define `main` and `bar` variables once during page load.
2.  During the scroll:
    1.  Calculate, where the target element starts (in pixels from document top).
    2.  If the user has started scrolling inside the target element:
        1.  Count the ratio (a decimal) indicating how much of the target element the user has already scrolled.
        2.  If the user reaches the end of document earlier than the bottom of the target element disappears, apply another formula for calculating progress: calculate how much the user has scrolled inside an area that starts at the point the target element starts and ends when document ends.
        3.  If the user is inside the target element (`progress <= 1`), set the progress bar width equals to previously calculated ratio converted to percents with two digits after comma.
        4.  If the user has scrolled the target element completely, set the width equals to 100% (sometimes the bar gets stuck somewhere below 100%, so fix it).
    3.  If the user hasn't started scrolling the target element, set the width equals to 0 (sometimes the bar gets stuck somewhere above 0%, so fix it).

**Tip:** sometimes it’s better to throttle scroll event and add `transition: all 50ms linear;` to progress bar in order to improve performance. This can help you avoid firing scroll event too often and maintain smooth animation at the same time.

As of April 4, 2019, IntersectionObserver is supported by 74% of web browsers, so I use scroll event instead.