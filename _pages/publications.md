---
layout: research
title: "Research"
permalink: /research/
redirect_from:
  - /publications/
author_profile: true
description: "Papers and ongoing projects on international trade, economic diplomacy, and the environment."
---

<div class="research-intro">
  <p>Papers and ongoing projects on international trade, economic diplomacy, and the environment.</p>
  {% if site.author.googlescholar %}
    <a class="research-scholar" href="{{ site.author.googlescholar | escape }}">Google Scholar <span aria-hidden="true">↗</span></a>
  {% endif %}
</div>

{% assign papers = site.publications | sort: 'date' | reverse %}
{% assign completed = papers | where: 'status', 'completed' %}
{% assign ongoing = papers | where: 'status', 'in_progress' %}

{% if completed.size > 0 %}
<section class="research-section" aria-labelledby="research-papers">
  <h2 id="research-papers" class="research-section-title">Papers</h2>
  <div class="research-grid">
    {% for post in completed %}
      {% include research-card.html %}
    {% endfor %}
  </div>
</section>
{% endif %}

{% if ongoing.size > 0 %}
<section class="research-section" aria-labelledby="research-progress">
  <h2 id="research-progress" class="research-section-title">Work in progress</h2>
  <div class="research-grid">
    {% for post in ongoing %}
      {% include research-card.html %}
    {% endfor %}
  </div>
</section>
{% endif %}
