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
      <h3><a href="{{ site.url }}{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h3>
    </li>
  {% endif %} <!-- <--- FONDAMENTALE: Chiude il controllo prima di passare al post successivo -->
{% endfor %}
  <h3> <li> <a href="/eventi/">Eventi</a> </li> </h3>
  <h3> <li> <a href="/newsletter/">Newsletter</a> </li> </h3>
</ul>
