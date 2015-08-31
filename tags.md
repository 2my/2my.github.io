---
layout: bootstrap
title: Categories
---
## Categories:
{% for category in site.categories %}
  * [{{ category | first }}](#{{ category | first }})
{% endfor %}

## Articles by Category:
{% for category in site.categories %}
### [{{ category | first }}]({{ category | first }})
  {% for posts in category %}
    {% for post in posts %}
	* [{{ post.title }}]({{ post.url }})
    {% endfor %}
  {% endfor %}
{% endfor %}
