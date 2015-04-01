---
layout: page
title: Search
isAlCat: true
---

<div class="posts">
  {% for post in site.posts %} 
    {% if post.categories contains 'algorithms' %}
      {% if post.alcat contains 'search' %}
        <div class="post">
        <hr style="height:5px;border:none;color:#333;background-color:#333;">
          <h2 class="post-title">
            <a href="{{ post.url }}">
              {{ post.title }}
            </a>
          </h2>

          <span class="post-date">{{ post.date | date_to_string }}</span>

          {{ post.content | strip_html | truncatewords: 20 }}
          <br>
            <a href="{{ post.url }}">
              Read More &rarr;
            </a>
        </div>
      {% endif %}
    {% endif %}
  {% endfor %}
  <hr style="height:5px;border:none;color:#333;background-color:#333;">
</div>