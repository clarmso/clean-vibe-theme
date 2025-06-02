---
layout: default
title: Blog
permalink: /blog/
pagination:
  enabled: true
---

<h1>Blog 📔</h1>

<ul>
  {% for post in paginator.posts %}
    {% unless post.unlisted %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a> - <small>{{ post.date | date: "%B %d, %Y" }}</small>
      </li>
    {% endunless %}
  {% endfor %}
</ul>

<!-- Pagination Links -->
{% if paginator.total_pages > 1 %}
  <nav class="pagination-nav">
    {% if paginator.previous_page %}
      <a class="prev" href="{{ paginator.previous_page_path }}">⬅️ Previous</a>
    {% else %}
      <span></span>
    {% endif %}
    {% if paginator.next_page %}
      <a class="next" href="{{ paginator.next_page_path }}">Next ➡️</a>
    {% else %}
      <span></span>
    {% endif %}
  </nav>
{% endif %}