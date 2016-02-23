---
layout: page
title: Blog
permalink: /blog/
description: This is where I write.
---
{% for post in site.posts %}
{% if post.type == "blog" %}
<div class="row">
    <div class="col-lg-8 col-lg-offset-2">
        <p><bd>{{ post.date | date: "%b %-d, %Y" }}</bd></p>
        <h4>{{ post.title }}</h4>
        <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
        <p><a href="{{ post.url | prepend: site.baseurl }}">Continue Reading...</a></p>
        <hr>
    </div>
</div>
{% endif %}
{% endfor %}
<div class="row">
    <div class="col-lg-8 col-lg-offset-2">
        <p class="rss-subscribe">Subscribe <a href="{{ "/feed.xml" | prepend: site.baseurl }}">via RSS</a></p>
    </div>   
</div>
