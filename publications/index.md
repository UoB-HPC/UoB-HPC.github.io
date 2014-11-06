---
title: Publications
---

<dl>
  {% for pub_hash in site.data.publications %}
  {% assign pub = pub_hash[1] %}
    <dt>{{ pub.title }}</dt>
    <dt>{{ pub.authors | array_to_sentence_string }}</dt>
    <dt><a href="{{ pub.url }}">Link</a></dt>
  {% endfor %}
</dl>
