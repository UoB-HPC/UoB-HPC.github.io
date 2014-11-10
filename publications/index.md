---
title: Publications
---

{% for pub in site.data.publications %}
<div class="publication">
  <dl>
    <dt>{{ pub.title }}</dt>
    <dt>{{ pub.authors | array_to_sentence_string }}</dt>
    <dt>{{ pub.date }}</dt>
    <dt>{{ pub.reference }}</dt>
  </dl>
</div>
{% endfor %}
