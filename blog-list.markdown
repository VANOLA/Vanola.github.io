---
layout: page
title: Blog
permalink: /blog/
---

{% for tag in site.tags %}
  {{ site.tags["Jekyll"].size }}
  <a href="/tag/{{ tag | first }}">{{ tag | first }}</a>
    Posts: {{ tag | last | size}}
{% endfor %}

  