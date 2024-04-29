---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{https://scholar.google.com/citations?user=kApGnjIAAAAJ&hl=es}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% if post.status == 'completed' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

## Work in Progress

{% for post in site.publications reversed %}
  {% if post.status == 'in_progress' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

---
layout: default
title: "Debugging Publications"
---

<h1>Publications in Collection</h1>
<ul>
{% for post in site.publications %}
  <li>{{ post.title }}</li>
{% endfor %}
</ul>

