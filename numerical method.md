---
layout: page
title: Numerical Method
---

<h3>{{ site.tags[0] }}</h3>
<ul>
  {% for post in tag[1] %}
    <li><a href="{{ post.url }}">{{ post.date | date: "%B %Y" }} - {{ post.title }}</a></li>
  {% endfor %}
</ul>
