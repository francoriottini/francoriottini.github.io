---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{ author.googlescholar }}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% if post.status == 'completed' %}
    {% assign is_published = false %}
    {% if post.published == true or post.published == "true" %}
      {% assign is_published = true %}
    {% endif %}

    {% if is_published %}
      {% include archive-single.html %}
    {% else %}
      <div class="archive-single">
        <h2 class="archive-title"><a href="{{ post.permalink }}">{{ post.title }}</a></h2>
        <p>{{ post.type | default: "Unpublished" }} ({{ post.date | date: "%Y" }})</p>
        <p>{{ post.excerpt }}</p>
        {% if post.paperurl %}
          <p>Download: <a href="{{ post.paperurl }}"><u>PDF</u></a></p>
        {% endif %}
      </div>
    {% endif %}
  {% endif %}
{% endfor %}

## Work in Progress

{% for post in site.publications reversed %}
  {% if post.status == 'in_progress' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}
