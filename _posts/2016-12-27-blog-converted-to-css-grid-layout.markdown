---
title: I Converted My Blog to CSS Grid Layout and Regret Nothing
categories:
- Design
layout: post-with-grid
description: Since the Web became a more beautiful place with the advent of CSS, there’s
  always been a struggle in the use of more modern features of CSS with browsers who
  are either slower to adopt or more cautious in the way the implement features. There
  have been many potential solutions for this issue.
---

With the death of Lella Vignelli last week (Dec. 21, 2016), I read for the first time The Vignelli Canon.

<aside class="reference">
    <p>The Vignelli Canon is amazing for a whole host of reasons other than just it's simple layout. If you're interested at all in design, <a href="http://www.vignelli.com/canon.pdf">please read it</a>.</p>
</aside>

The layout of the pages inspired me. I knew that I wanted to give a quick update to some of my blog posts to mirror some of the design from that book -- a book that talks about grids, as well.

To do this, I decided to convert my blog posts to CSS Grid Layout.

With the release of this blog post, I'm also releasing the updated code into the wild.

<aside class="reference">
    <p>If you're looking at this and all you see is a centered column, your browser doesn't support Grid yet. <a href="https://developers.google.com/web/updates/2014/03/Get-on-the-CSS-Grid">Find out how to enable Grid to see this as intended</a>.</p>
</aside>

This is a super simple implementation and doesn't look quite right in the Firefox Developer build, due to height bugs, but it's really nice in other experimental browsers -- such as Chrome with the experimental flag checked.

I've only converted one other blog post to the new layout at this point. Fittingly, it's my post on [Grid and Feature Queries](/blog/2016/12/17/feature-queries-on-the-rise/).

I won't dive into too many details, but here's a snippet of some of the CSS I'm using to accomplish this layout.

<aside class="reference">

<p>If you're interested in more, <a href="http://codepen.io/brob/pen/ZBZqOQ">here's a CodePen where I'm experimenting more with layout</a>. This is also where I started laying this out.</p>

</aside>

{% highlight css linenos %}
.post {
    /* Sets this to be a grid,
    defines the columns and adds margin between rows */

    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    grid-row-gap: calc(.8rem + .5vw);
}

.post > p, .post > iframe, .post > .highlight {
    /* Sets my blog content to span the last 3 columns
    (using > p instead of a class
    to make my life easy with markdown) */

    width: 100%;
    grid-column: 3 / span 3;
}

aside {
    /* Sets asides to start at the first column line
    and spans the aside 2 columns */
    grid-column: span 2;
}

{% endhighlight %}

<aside class="subhead">
    <h2>A couple example posts</h2>
</aside>

<aside class="reference">
    <p>This post's implementation. On the left: CSS Grid. On the right: Fallback to non-supported browsers</p>
</aside>
![Example Grid Layout Number 1](/images/blog/grid/side-by-side2.jpg)

<aside class="reference">
    <p><a href="/blog/2016/12/17/feature-queries-on-the-rise/">My post on Feature Queries</a>. On the left: CSS Grid. On the right: Fallback to non-supported browsers</p>
</aside>

![Example Grid Layout Number 1](/images/blog/grid/side-by-side.jpg)
