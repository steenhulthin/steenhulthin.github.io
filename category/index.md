---
layout: blogpost
date: 2014-09-18
---
# Categories

{% for category in site.categories %}
  <li><b name="{{ category | first }}">{{ category | first }}</b>
    <ul>
    {% for posts in category %}
      {% for post in posts %}
        {% if post.title != nil %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
        {% endif %}
      {% endfor %}
    {% endfor %}
    </ul>
  </li>
{% endfor %}