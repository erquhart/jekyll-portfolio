---
layout: post
title: I Present
comments: "off"
---


## Invite me to speak at your conference

I'm currently presenting two main topics: "Post-Modern CSS" and "You're a Designer; I promise."


## Upcoming Conferences


## Presentations and Resources


{% for presentation in site.presentations %}
    <article class="stripe {% cycle 'neutral', 'primary' %}">
        <h3 class="stripe_headline"><a href="{{ presentation.url }}">{{ presentation.title }}</a></h3>
        <div class="stripe_description">
            <p>{{ presentation.description }}</p>
            <a href="{{ presentation.url }}" title="{{ presentation.title }}">Read More &raquo;</a>
        </div>
    </article>
{% endfor %}
