---
layout: bootstrap
title: Categories
---
<br/>
<!-- http://jekyllrb.com/docs/variables/ -->
## Categories:
{% for category in site.categories %}
  * [{{ category | first }}](#{{ category | first }})
{% endfor %}

## Articles by Category:
{% for category in site.categories %}
### {{ category | first }}<a name="{{ category | first }}">&nbsp;</a>
  <ul>
  {% for posts in category %}
    {% for post in posts %}
      {% if 0 < post.url.size %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      {% endif %}
    {% endfor %}
  {% endfor %}
  </ul>
{% endfor %}

