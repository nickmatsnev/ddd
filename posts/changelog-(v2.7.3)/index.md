---
title: "Changelog (v2.7.3)"
date: 2019-06-26
tags: [News]
draft: true
featured_image: logo.png
summary: This update addresses a few big changes and several minor improvements.
scripts: [relative_date.js]
---

## Update 2.7.3

Moved to Hugo awaiting new redesign!

## Update 2.7.2

- The bug when all JS scripts failed to execute in Safari was fixed.
- Footer layout was changed.
- Blog page navigation became simpler.
- Snippets were updated.
- Unnecessary wrappers were removed.
- SVGs became cacheable.
- Print styles were moved to a separate file.
- Search results now show the headings when there are several types of content found.

## Update 2.7.1

- Image zooming animation became more consistent.
- Now you can click on the heading to get an anchor link.
- Blog posts now occupy full width on small screens.
- Blog post header now has center alignment on small screens.
- Fonts were subsetted and compressed in order to save extra kilobytes of bandwidth.

## Update 2.7

- Blog page layout was completely redesigned.
- UP button became a bit smaller.
- Code blocks’ margins were fixed.
- Comments block was moved under the main section.
- Footer became simpler and now sticks to the bottom.
- Project page credits section, comments, top menu, project thumbnail styles were rewritten to decrease CSS payload.
- Fonts self-hosting made it possible to use `font-display: swap`.
- Assets are now served uncombined to increase loading speed by taking advantage of HTTP/2.
- Images now affect approximate reading time.
- Snippets page was completely redesigned.
- Tools page was redesigned as well.
- Top menu icons were changed.
- Every Russian piece of text was translated into English, making it possible not to serve both Latin and Cyrillic fonts.
- The bug when search input didn’t occupy all the top menu height in Safari was fixed.
- cssnano and mqpacker are now working on minifying the CSS (before it was compressed by built-in Autoptimize compressor).
- UglifyJS is now working on minifying the JS (before it was compressed by built-in Autoptimize compressor).
- Now all the dates earlier than 2 months will be displayed relatively formatted.

## Update 2.6

- A tiny snippet replaced original the Google Analytics script.
- Print styles were added.
- WebP images that were bigger than their originals were deleted.
- All SVG images were optimized.
- The grammar and punctuation were fixed everywhere to comply with the rules of American English.
- Reading progress now recalculates on window resize.
- The small .vk social icon became bigger to match other icons.
- When the user starts selecting the code, the new notification about “double-click to copy” functionality will appear.
- [Quicklink](//github.com/GoogleChromeLabs/quicklink) is now used across the website.
- The formula for calculating approximate reading time was changed a bit.
- Other minor improvements.

## Update 2.5

- Reading progress bar color was fixed in WebKit.
- Added WebP support.
- Blockquote behaves better on small screens now.
- The issue with big link font size in comment text was fixed.
- Thanks to prerendering, blog page now loads faster.
- The issue, when comments section overlapped zoomed image was fixed.
- The issue, when IO table went off the screen in Chrome was fixed.
- JavaScript functions’ scopes were fixed.
- HSTS policy was set.
- Prism.js now loads only if there is a “highlightable” block in the DOM, saving ~20 KB where it’s not needed.
- UP button became more responsive.
- Google Analytics scripts now load a bit faster.

## Update 2.4

- Zoom functionality for images was implemented.
- Reading progress indicator was added.
- Bugs caused by doubled margins were fixed.
- All images got their heights and widths back.
- A bug when the user could not return to the previous position after clicking UP button in Edge was fixed.
Search input placeholder now has the same color in all browsers.
- `<pre>` now has the same selection color in all browsers.
- `::before` and `::after` pseudo-elements now have `box-sizing: border-box`.
- Blog page now serves smaller thumbnails, overall page size became smaller by 17%.
- `<time>` elements got `datetime` attributes.
- The homepage does not load Roboto Mono anymore.
- Accessibility was improved a bit (colors became more contrast, ARIA attributes were added, focus behavior was fixed).
- Missing preconnects were added.

## Update 2.3

Since the previous update I have:

- fixed UI bugs when surfing without JS.
- made top menu a bit smaller and more responsive.
- fixed project title overlap.
- added some neat animations on project pages.
- made UP button full height, so that it is easily clickable.
- made UP button work via <kbd>W</kbd> button.

## Update 2.2

- The selection inside code blocks got its own color.
- Double click inside code blocks will select code inside.
- The top menu became smaller.
- Typography on mobile devices was improved.
- Recent posts are now displayed at the top of the blog page.
- Comments were fixed (in some cases it was impossible to leave a reply to another comment).
- HTML was rewritten in order to be semantic.
- The homepage now serves its own CSS file, which is much smaller.
- Terminal block lost its header and now has `overflow: auto`.

## Update 2.1

The main page was completely redesigned. I tried to make a step towards minimalism, to get rid of small text blocks, narrow project thumbnails. Now you can see a huge text about me and what I do. Once you scroll down, you are likely to see big thumbnails of projects I’ve done.

Another thing to be reinvented was the top menu. I’ve got rid of unimportant information and links, enriched the new menu with icons. Now it looks pretty cool.

- Footer icons have the same hover colors.
- The UP-DOWN button was added.
- All elements that had rounded corners lost them.
- New project thumbnail hover animation.
- The font became responsive, huge headings are displayed correctly on small screens.
- New snippets page.
- Code blocks became full-width.
- New layout for blog post headings.

## Update 2.0

Here is an update note about changes applied to my website since March 2018. Update 2.0 primarily affected the backend part of kottsov.com, but had a few effects on the front. Now I want to review the key changes I’ve made.

### Projects
One of the main content types on my website is a project. This update had a great effect on this. First of all, the appearance of each project post has changed a little: I removed dates and links from the thumbnails, as they were difficult to use. Now project thumbnails nicely stretch, fitting the screen width and height despite their own size.

Secondly, I’ve created a new way of displaying headers. Now they can be:

- **White**  
If there is a dark thumbnail.
- **Black**  
If there is a bright thumbnail.
- **Black with white background**  
If the background contains a complicated image so that none of the above header types can be used.

Now it comes to backend changes. The way I handle every project has completely changed. Now I use Custom Post Type instead of a particular category to group projects, and Metaboxes instead of Custom Fields to display metadata. It gave me better flexibility in editing projects.

### Announces
I added another Custom Post Type called Announce. It will be used to display some relevant information inside The Project Gallery on the main page. It has the same size and style as a project but contains the text instead of project meta.

### Search
The search was greatly improved. Now it allows searching for any post, project, category, tag or meta. Now you can easily find posts of the exact category, a project with a particular tag and so on. Search results are now grouped by project-first principle.

### Blog page
The blog page has been completely redesigned. Now posts are divided into categories and displayed in perfect beautiful grids. The annoying animation on hover was removed, blog post links at the bottom were changed.

### New blocks
I also added a new block called `.terminal` which looks like this.

<div class="terminal">
Microsoft Windows [Version 10.0.16299.431]<br>
(c) 2017 Microsoft Corporation. All rights reserved.
</div>

### Miscellaneous
Some minor changes:

- Now I use Highlight.js and Atom One Dark theme to highlight the code.
- CSS was written from scratch.
- The logo had a little change.
- The number of different colors used was reduced.
- Body width was increased up to 1000px.
- Search icon was replaced.
- New links colors.
- Better responsiveness with less code due to using modern CSS technologies such as grid and flexbox.
- Comment template was rewritten in order to implement better alignment without magic integers.