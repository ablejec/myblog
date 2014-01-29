---
title: About statistics, R, graphics and ...
layout: page
---

<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator">{{ y }}</li>
  {% endif %}
  <li class="listing-item">
    <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
    <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    <p>{{ post.excerpt }} 
<span class="more"> <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">more ...</a></span>
    </p>
  </li>
{% endfor %}
</ul>

