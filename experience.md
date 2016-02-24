---
layout: page
title: Experience
permalink: /experience/
description: Out in the real world.
---

{% for post in site.posts %}
{% if post.type == "experience" %}
<div class="row">
    <div class="col-lg-8 col-lg-offset-2">
        <p><bd>{{ post.date | date: "%b %-d, %Y" }}</bd></p>
        <h4><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h4>
        <p>{{ post.content | strip_html | truncatewords: 50 }}</p>
        <p><a href="{{ post.url | prepend: site.baseurl }}">Continue Reading...</a></p>
        <hr>
    </div>
</div>
{% endif %}
{% endfor %}

<div class="row">
    <div class="col-lg-8 col-lg-offset-2 centered">
        There is currently nothing here, but soon... there shall be.
    </div>
</div>
