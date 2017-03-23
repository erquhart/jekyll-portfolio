---
title: Make a More Flexible Cover Screen with CSS Grid
categories:
- Development
- Design
layout: interior
description: Our design trends are about to get a facelift. Grid Layout is coming in the next release of modern browsers. It's important to get a grip on its utility. Let's take a common trend in editorial and marketing design - the "cover page" banner area.
---

<div class="container container-narrow">
    <p>Our design trends are about to get a facelift. Grid Layout is coming in the next release of modern browsers. It&#39;s important to get a grip on its utility.&nbsp;</p>

    <p>Let&#39;s take a common trend in editorial and marketing design: the "cover page" banner area.</p>

    <img src="/images/blog/grid-cover/simple-cover.jpg" alt="">

    <p>At its simplest, this contains five elements: headline, subhead, byline, photo and photo credit.</p>

    <p>This is a bold design pattern.&nbsp;</p>

    <p>With current CSS, it&#39;s also a static design pattern. Each article detail page is laid out the same. The only difference is the background image.</p>

    <p>With CSS Grid, we take similar markup on each page and can apply unique layout. This opens the door to art direction for each article.&nbsp;</p>

    <p><em>Author&#39;s note: For simplification the examples in this article won&#39;t use Feature Queries to ensure support. See my post on <a href="/blog/2017/01/18/your-code-should-fall-forward/">Feature Queries for more information on implementing Grid while supporting non-compliant browsers</a>.</em></p>

    <p><em>Second author&#39;s note: I can envision some great CMS interfaces using this method. Selectable grid areas in a CMS would be amazing and super flexible.</em></p>

    <p>To get to the point of flexibility, we first have to set up our template. &nbsp;The .headline, .subhead and .secondary are all children under our grid container.</p>

    <img src="/images/blog/grid-cover/grid-setup.gif" alt="">

    {% highlight scss %}
.cover {
    box-sizing: border-box;
    width: 100%;
    height: 100vh; // Always 100% of the viewport's height
    padding: 20px;

    display: grid;
    grid-template-rows:    1fr 1fr 1fr 1fr 1fr; // 5 rows
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr; // 5 columns
    grid-gap: 5px;
    // 5x5 works well for centering
}
{% endhighlight %}


    <p>After we write our HTML and set up our grid in CSS, we&#39;re ready to place our content. Here&#39;s an example of the basic "cover" layout:</p>



    <img src="/images/blog/grid-cover/grid-easy-image.jpg" alt="">

    <p>To layout a headline, subhead and caption this simply, Grid may be a bit of overkill. Here's the code for the image above:</p>

    {% highlight scss %}


.headline {
    grid-row: 3;
    grid-column: 2 / 5;
    text-align: center;
    align-self: center;
    align-self: end;
}
.subhead {
    grid-row: 4;
    grid-column: 2 / 5;
    text-align: center;
}
.secondary {
    grid-column: 4 / 6;
    text-align: right;
}

    {% endhighlight %}

    <p>Flexbox and absolute positioning would probably have made this easier. This setup also allows us to use the 5x5 grid to create new and powerful combinations based on the same markup.</p>


    <p>We can allow our image to dictate the needs of our content. We can also allow the text to speak to our articles theme. In other words, we can art direct on the web (<a href="http://jensimmons.com/presentation/revolutionize-your-page-real-art-direction-web">inspiration from Jen Simmons for this language</a>).</p>


    <h2>Example 1: Skyline</h2>


    <img src="/images/blog/grid-cover/skyline-image.jpg" alt="">

    <p>In our first example, we&#39;ve got a beautiful shot of a city skyline blazing in the night.</p>

    <p>There would still be impact if we left our headline in its default position, but the headline will compete with the image. What if the text could mirror the shape of a skyscraper? What if it could also fit within the negative space afforded by the walkway?</p>

    {% highlight scss %}
.headline {
    grid-row: 2 / 6;
    grid-column: 3 / 4;
    text-align: center;
    align-self: end;
}
.secondary {
    grid-row: 5 / 6;
    grid-column: 4 / 6;
    text-align: right;
}
    {% endhighlight %}

</div>

<img src="/images/blog/grid-cover/grid-center-column.jpg" alt="">

<div class="container container-narrow">
    <h2>Example 2: Connecting eye line to headline</h2>

    <p>The images we choose can also help direct a user's eye where we want it to go.</p>

    <img src="/images/blog/grid-cover/forest-image.jpg" alt="">

    <p>Not only does this image have a striking subject and color scheme, it also places its subject in an awkward spot for designers.</p>

    <p>In this example, we can eschew the tradition of placing our headline at the center or on the left side of the screen. Instead, we work with our image to allow the woman's eye line to connect the user to our headline in an atypical design.</p>

</div>

<img src="/images/blog/grid-cover/forest-static.jpg" style="width: 80%; margin: 0 auto 20px; display: block;" alt="">

<div class="container container-narrow">

    <p>Again, we can simply change our CSS to change our layout. No need to modify markup.</p>

    {% highlight scss %}
.headline {
    grid-row: 2 / 5;
    grid-column: 5 / 6;
    text-align: right;
    font-family: 'Stalemate', cursive;
}
.subhead {
    grid-column: 3 / 6;
    grid-row: 6;
    text-align: right;
}
.secondary {
    grid-row: 6;
    grid-column: 1 / 3;
}
{% endhighlight %}
</div>


<div class="container container-narrow">
    <h2>More examples</h2>

    <p>Here are other screenshots for ways of laying out content in a cover page via the same grid and markup we've used so far. All of these layouts are available to play with <a href="">in my CodePen collection</a>. If you use them in CodePen, keep in mind, you'll need to have a Grid-enabled  browser.</p>

</div>

<div class="container grid-thirds">
    <img src="/images/blog/grid-cover/room.jpg" alt="">
    <img src="/images/blog/grid-cover/architecture.jpg" alt="">

</div>
