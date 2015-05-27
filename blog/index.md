---
layout: page
title: Blog
---

{% for post in site.posts %}

<h1 class="post-title">
  <a href="{{ site.baseurl }}{{ post.url }}">
    {{ post.title }}
  </a>
</h1>

by
**{{ post.author }}**
on <time datetime="{{ post.date | date_to_xmlschema }}" class="post-date">
**{{ post.date | date_to_string }}**
</time>
{{ post.content }}

{% endfor %}
