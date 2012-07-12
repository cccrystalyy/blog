---
title: Keep on Fighting!
layout: default
---

<<<<<<< HEAD
<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator">{{ y }}</li>
  {% endif %}
  <li class="listing-item">
    <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>

=======
<div>
  <ul class="listing">
  {% for post in site.posts limit: 2 %}
  <article class="content">
    <section class="title">
      <h2><a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></h2>
    </section>
    <section class="meta">
    <span class="time">
      <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    </span>
    {% if post.tags %}
    <span class="tags">
      {% for tag in post.tags %}
      <a href="/tags.html#{{ tag }}" title="{{ tag }}">#{{ tag }}</a>
      {% endfor %}
    </span>
    {% endif %}
    </section>
    <section class="post">
    {{ post.content }}
    </section>
    </article>
  {% endfor %}
  </ul>
  <div class="center">
  <a href="{{ site.url }}/archive.html" class="circle-wrapper">
  <div class="circle">&nbsp;</div>
  <div class="circle">&nbsp;</div>
  <div class="circle">&nbsp;</div>
  </a>
  </div>
</div>
>>>>>>> Fix Url
