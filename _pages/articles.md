---
layout: single
title: "Technical Articles & Research"
permalink: /articles/
author_profile: true
---

A collection of my thoughts on AI, Data Science, and Computer Engineering.

{% for post in site.posts %}
  <div class="list__item">
    <article class="archive__item">
      <h2 class="archive__item-title">
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </h2>
      <p class="archive__item-excerpt">{{ post.excerpt | strip_html | truncate: 160 }}</p>
      <span class="page__meta">{{ post.date | date: "%B %d, %Y" }}</span>
    </article>
  </div>
  <hr>
{% endfor %}
