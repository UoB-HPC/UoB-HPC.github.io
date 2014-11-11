---
title: Publications
---

{% for pub in site.data.publications %}
**{{ pub.title }}**  
{{ pub.authors | array_to_sentence_string }}  
{{ pub.date }}  
{{ pub.reference }}

{% endfor %}
