---
layout: page
title: research
permalink: /research/
description: 
nav: true
nav_order: 4
display_categories: [constructor theory, math, p2p, neuroscience]
horizontal: false
---

<!-- pages/research.md -->
<div class="research">
{%- if site.enable_research_categories and page.display_categories %}
  <!-- Display categorized research -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_research = site.research | where: "category", category -%}
  {%- assign sorted_research = categorized_research | sort: "importance" %}
  <!-- Generate cards for each research -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for research in sorted_research -%}
      {% include research_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for research in sorted_research -%}
      {% include research.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display research without categories -->
  {%- assign sorted_research = site.research | sort: "importance" -%}
  <!-- Generate cards for each research -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for research in sorted_research -%}
      {% include research_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for research in sorted_research -%}
      {% include research.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
