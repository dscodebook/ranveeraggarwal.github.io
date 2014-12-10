---
layout: page
title: Algorithms
custattr: side
---

At times, I *do* try my hands on algorithmic coding. In process, I tend to find some algorithms/hacks/tricks that impress me. To share those with you and also keep them as a reference, I have described some of them in the following sections.

<hr style="height:5px;border:none;color:#333;background-color:#333;">

<div class="posts">
  <h3>Categories</h3>
  <ul>
	{% assign pages_list = site.pages %}
	{% for node in pages_list %} 
    {% if node.title != null %}
      {% if node.layout == "page" %}
        {% if node.isAlCat == true %}
    		  <li><a href="{{ node.url }}">{{ node.title }}</a></li>
          <br>
        {% endif %}
      {% endif %}
    {% endif %}
	{% endfor %}
  </ul>
</div>
<!--div class="posts">
  {% for post in site.posts %} 
    {% if post.categories contains 'algorithms' %}
    <div class="post">
    <hr style="height:5px;border:none;color:#333;background-color:#333;">
      <h2 class="post-title">
        <a href="{{ post.url }}">
          {{ post.title }}
        </a>
      </h2>

      <span class="post-date">{{ post.date | date_to_string }}</span>

      {{ post.content | strip_html | truncatewords: 50 }}
      <br>
        <a href="{{ post.url }}">
          Read More &rarr;
        </a>
    </div>
    {% endif %}
  {% endfor %}
  <hr style="height:5px;border:none;color:#333;background-color:#333;">
</div-->