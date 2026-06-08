---
layout: page
show_meta: false
subheadline: "Eventi settimanali e realtà"
title: "Dove andiamo?"
header:
   image_fullwidth: "header_unsplash_5.jpg"
permalink: "/dove-andiamo/"
---
<ul>
{% for post in site.posts %}
  {% if post.categories contains 'attività' or post.tags contains 'realtà' %}
    <li>
      <a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endif %} <!-- <--- FONDAMENTALE: Chiude il controllo prima di passare al post successivo -->
{% endfor %}
    <li> <a href="/eventi/">Eventi</a> </li>s
</ul>
