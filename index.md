---
title: About statistics, R, graphics and ...
layout: page
---

<ul class="tags">
{% for category in site.categories %}
    <li style="font-size: {{ category | last | size | times: 100 | divided_by: site.categories.size | plus: 70 }}%">
        <a class="tag"  href="/categories/#{{ category | first | slugize }}/">
            {{ category | first }}
        </a>
    </li>
{% endfor %}
</ul>

<ul class="listing">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <li class="listing-seperator">{{ y }}</li>
  {% endif %}
  <li class="listing-item">
    <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
    <p>{{ post.excerpt }} &nbsp; 
<div align="right"> 
<time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time> &nbsp;
<a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">more...</a></div>
</p>
  </li>
{% endfor %}
</ul>

